---
description: Ansible fundamentals
coverY: 0
---

# Learn Ansible

## <mark style="color:blue;">What is Ansible</mark>

* Ansible is a tool used to automate IT tasks.
* It is agentless so we do not need to install agents for the tool on our servers, we can just access a machine by SSH and run a YAML script.&#x20;

## <mark style="color:blue;">How ansible works</mark>

* Use of modules : Small program that do the actual work. It is sent from our machine to the different servers. They do their work and get removed. Each module do one specific small task, so for example we can have one module to install an nginx server, start docker container...
* So Ansible has a lot of modules for differents tasks, so there is a high chance that we find a module that responds to our demand of executing a specific IT task.

## <mark style="color:blue;">Ansible playbooks</mark>

* Ansible playbook is a set of different modules grouped together in a certain sequence to acheive a goal
* The different modules are stored in a variable called tasks &#x20;

&#x20;<mark style="color:blue;">------------------------------------------------------------------------------------------------</mark>

&#x20; **  `tasks:`**

&#x20;    `-`<mark style="color:green;">`name`</mark>`: Rename table foo to bar`

&#x20;        <mark style="color:yellow;">`postgresql_table`</mark>`:`

&#x20;            <mark style="color:purple;">`table`</mark>`: foo`

&#x20;            <mark style="color:purple;">`rename`</mark>`: bar`

<mark style="color:green;"></mark>

<mark style="color:green;">Description of task</mark>

<mark style="color:yellow;">module name</mark>

<mark style="color:purple;">arguments for module</mark>



We can also execute multiple modules in a sequence so each module after the other and these modules can be related to each other.

&#x20;<mark style="color:blue;">------------------------------------------------------------------------------------------------</mark>&#x20;

Now we will see the **hosts** variable  that let ansible know on which machine we want the playbook to be executed



**`-hosts:`**`databases`

&#x20; **  `remoteuser:`**`root`&#x20;

&#x20; **  `tasks:`**

&#x20;    `-`<mark style="color:green;">`name`</mark>`: Rename table foo to bar`

&#x20;        <mark style="color:yellow;">`postgresql_table`</mark>`:`

&#x20;            <mark style="color:purple;">`table`</mark>`: foo`

&#x20;            <mark style="color:purple;">`rename`</mark>`: bar`

&#x20;

So here it will be executed on databases host with the user root.

&#x20;<mark style="color:blue;">------------------------------------------------------------------------------------------------</mark>

We can also define varibales for repeated values :&#x20;

**`-hosts:`**`databases`

&#x20; **  `remoteuser:`**`root`&#x20;

&#x20; **  `vars:`**

&#x20;       **        `tablename:`**` ``foo`

&#x20;       **        `tableowner:`**` ``someuser`
