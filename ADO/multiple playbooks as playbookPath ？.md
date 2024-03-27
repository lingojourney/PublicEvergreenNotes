In Ansible, if you want to run multiple playbooks, you can aggregate them using `import_playbook` statements within a main playbook. Here’s an example of how you might structure your main playbook to include multiple playbooks:

```yaml
---
- import_playbook: playbook-one.yml
- import_playbook: playbook-two.yml
- import_playbook: playbook-three.yml
```

Each playbook will run in the order they are listed. If you need to run playbooks in parallel, Ansible doesn’t support this directly within a single process. [You would need to execute each playbook as a separate process](https://serverfault.com/questions/750856/how-to-run-multiple-playbooks-in-order-with-ansible)[1](https://serverfault.com/questions/750856/how-to-run-multiple-playbooks-in-order-with-ansible)[2](https://stackoverflow.com/questions/66202726/how-to-run-multiple-playbooks-in-parallel).

For running multiple tasks within a playbook concurrently, you can use the `async` and `poll` keywords. [The `async` keyword triggers the job in the background and can be checked later, while the `poll` value indicates how often Ansible should poll to check on the task completion](https://serverfault.com/questions/750856/how-to-run-multiple-playbooks-in-order-with-ansible)[2](https://stackoverflow.com/questions/66202726/how-to-run-multiple-playbooks-in-parallel).

[Remember to ensure that each playbook is a closed process and does not rely on the state or variables from another playbook](https://serverfault.com/questions/750856/how-to-run-multiple-playbooks-in-order-with-ansible)[1](https://serverfault.com/questions/750856/how-to-run-multiple-playbooks-in-order-with-ansible).

# Conditional 
In Ansible, you can conditionally import a playbook using the `when` clause. This allows you to specify conditions under which a playbook will be imported and executed. Here’s an example of how you can use the `when` clause with `import_playbook`:

```yaml
---
- import_playbook: some-playbook.yml
  when: some_condition

- import_playbook: another-playbook.yml
  when: another_condition
```

In this example, `some_condition` and `another_condition` are placeholders for actual conditions that you would define based on your requirements. These conditions can be based on variables, facts, or the results of previous tasks.

For instance, if you have a variable `deploy` that determines whether to run a deployment playbook, you could do something like this:

```yaml
---
- import_playbook: deploy-app.yml
  when: deploy == true
```

The `deploy-app.yml` playbook would only be imported and executed if the `deploy` variable is set to `true`.

[Remember, the conditions are evaluated at the time playbooks are imported, so any variables or facts used in conditions must be set before the `import_playbook` task](https://stackoverflow.com/questions/62118694/how-to-run-ansible-playbook-conditionally)[1](https://stackoverflow.com/questions/62118694/how-to-run-ansible-playbook-conditionally).