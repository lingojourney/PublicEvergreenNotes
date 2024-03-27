
# Do "register" values have to be unique? 
In Ansible, “register” is a keyword used to capture the output of a task and save it into a variable. This allows you to use the results of one task in subsequent tasks within the same playbook. [For example, you can check if a file exists and then use the result to decide whether to perform another action](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html)[1](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html)[2](https://marketsplash.com/tutorials/ansible/ansible-register/).

Here’s a simple example:

```yaml
- name: Check if a file exists
  stat:
    path: /path/to/file
  register: file_stat

- name: Display a message if the file exists
  debug:
    msg: "File exists"
  when: file_stat.stat.exists
```

In this case, `file_stat` is the registered variable that stores the output of the `stat` module, which checks for the existence of a file. [The `debug` task then uses this registered variable to conditionally display a message based on whether the file exists or not](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_variables.html)[2](https://marketsplash.com/tutorials/ansible/ansible-register/). Registers are very useful for handling dynamic data and adding conditional logic to your playbooks.