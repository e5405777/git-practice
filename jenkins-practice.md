# Jenkins Practice

Under Execute Shell, we can check which node the build is running on.

```bash
echo "Node name: $NODE_NAME"
echo "Hostname: $(hostname)"
echo "Workspace: $WORKSPACE"

In order run the job depend on the schedule 

<img width="823" height="314" alt="image" src="https://github.com/user-attachments/assets/66bd2673-85f3-47ad-ad60-b80948d7675e" />

## Downstream Job in Jenkins

Then create a second **Freestyle job**.

1. Add a **Build Step** and add the required command.
2. Once the first job completes, we need to call the second job. We call the second job the **downstream job**.
3. In the first job, go to **Post-build Actions**.
4. Select **Build other projects** / **Trigger parameterized build on other projects**, depending on the Jenkins configuration.
5. Select the second job that needs to be triggered.
6. Add the required condition, such as triggering the downstream job **only when the first job is successful**.

So the flow will be:

**First Job → Post-build Action → Second Job (Downstream Job)**


<img width="794" height="372" alt="image" src="https://github.com/user-attachments/assets/c677cbcf-a98f-42fe-87a7-e4a57c3e8195" />

if it's working fine next we need to add
py test.py for testing weather we are getting retrun status of last cmd


######next step
## Jenkins Interactive Build with User Input

Jenkins should run the job interactively, where the user is asked to provide some values before the job starts.

To achieve this:

1. Open the Jenkins job.
2. Click **Configure**.
3. Enable **This project is parameterized**.
4. Add the required parameter, such as:

   * String Parameter
   * Choice Parameter
   * Boolean Parameter
5. Enter the parameter name and default value if required.
6. Save the configuration.
7. Click **Build with Parameters**.
8. Jenkins will ask the user to provide the required values.
9. After the user submits the values, Jenkins will start the job and use those values during execution.

For example, create a **String Parameter**:

```text
Name: ENVIRONMENT
Default Value: dev
```

Then use the parameter in the **Execute Shell** build step:

```bash
echo "Environment: $ENVIRONMENT"
```

If the user selects or enters:

```text
ENVIRONMENT=production
```

Jenkins will execute:

```text
Environment: production
```

This allows the same Jenkins job to be executed with different user-provided values.

<img width="616" height="311" alt="image" src="https://github.com/user-attachments/assets/108c0a00-589e-45c7-8894-14a8caa44380" />

<img width="708" height="354" alt="image" src="https://github.com/user-attachments/assets/dbf966d8-e10e-4da1-9185-0587539a908c" />

in the execute shell
echo "-------------"
echo " Hi $FIRSTNAME $(FIRSTNAME)"
echo "------"

We can add the default value is students it will take automatically when we schedule the job

We have choice parameter

SECOND NAME
A
B
C
D
E

in the execute shell
echo "-------------"
echo " Hi $FIRSTNAME $SECONDNAME"
echo "------"


################
In the second job also add Project is parameterized

then select the string parameter

FIRSTNAME
NOVALUE
ENTER YOUR NAME

now in the down stream we need to pass the default value but we need install pulgin parametrized trigger

<img width="740" height="320" alt="image" src="https://github.com/user-attachments/assets/de9a2e14-307c-4e0e-9243-4d3afe1a5627" />

now still taking the default value

now we need to pass the parameter for the second job

current build parameters means what ever first job getting it passing to second job

<img width="804" height="382" alt="image" src="https://github.com/user-attachments/assets/3696285a-1437-4b15-abba-7519bcd12ac1" />

Parameter session add
FIRSTNAME=pavan

once run the build
then change the parameter
FIRSTNAME=pavan-$(FIRSTNAME)

<img width="443" height="151" alt="image" src="https://github.com/user-attachments/assets/f4768b49-a28b-494c-b8e7-0959d1a308e0" />

<img width="839" height="257" alt="image" src="https://github.com/user-attachments/assets/47a0c9a9-3fbf-49e4-ae21-2ff65b78ced6" />

What ever input getting from first job passing to second job

once this one tested we can select build on same node 


#########Maven installation steps ##########

cd /usr/local

sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.11/binaries/apache-maven-3.9.11-bin.tar.gz

sudo tar -xvzf apache-maven-3.9.11-bin.tar.gz

sudo ln -s apache-maven-3.9.11 maven

export M2_HOME=/usr/local/maven
export PATH=${M2_HOME}/bin:${PATH}

<img width="859" height="359" alt="image" src="https://github.com/user-attachments/assets/a6221ab7-e400-42f9-9efc-86a19aa33165" />

 


