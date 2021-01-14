Exercise 1: Dev tools & cloud
Introduction
This exercise sets up a development environment on your Windows, MacOS or Linux laptop/desktop for the remainder of the course. You will be using a mix of Azure and AWS.

Upon completing this exercise, you will be ready to handle subsequent exercises and your term project.

Please refer to the Exercise 1 FAQ and Exercise 1A FAQ for up-to-date answers on common problems. I will update them continually as new information rolls in.

1. Client tools
You will need to setup the appropriate tools on the machine you plan to use for this course's exercise, assignments, and project. The heavy lifting will be typically on the cloud side (AWS or Azure) but you will need a certain amount of tooling on your computer to operate the cloud.

The submission for this exercise will comprise the version information for these software. (Copy and paste the entire terminal output.) In your submission document, be sure to indicate which platform you used for this exercise in the top box. If you are using a CSIL lab machine for this exercise, most of the packages are installed already. You will still need to configure your account/access.

Note that section 1 is the installation; in many case, you will continue with configuration in section 2.

1.1 Editor
If you are not already using a GUI text editor, install Atom. Other good choices include Sublime Text and Visual Studio Code.

A good text editor raises your productivity significantly with syntax highlighting, syntax validation/hinting, support for multiple files/source trees, integration with version control (git) and numerous other creature comforts. Do not skip this step.

1.2 Package Manager
If you are not already using a package manager, install the appropriate one for your environment.

Platform	Package Manager
Windows (10+)	Chocolately
MacOS	Homebrew
Linux	Take your pick per your distro
You will use the corresponding package manager to simplify the install of subsequent packages.

1.3 git
Install git per the git community's instructions. In many environments (e.g., MacOS), git comes pre-installed; check.

Install Github Desktop too to complement the CLI git.

See here for a git cheatsheet. (Additional tutorial at DZone and a supervisual cheatsheet by Matt Harrison.)

1.4 Docker
Install docker & Docker Desktop from docker.com. If you have less than 8GB of RAM on your laptop, please upgrade. The alternative is to use CSIL/Blusson.

1.5 AWS
Install the AWS CLI per Amazon's instruction

Continue with eksctl.

1.6 Microsoft Azure
Install the Azure CLI per Microsoft's instruction

1.7 Google Cloud Platform
Install the gcloud CLI per Google's instruction

1.8 Kubernetes & friends
Install kubectl and k9s.

1.9 istio
Install istioctl per the istio community's instructions. Note that you do not need to install the entire istio package; just istioctl will suffice.

Install helm per the helm community's instructions

1.10 Gatling
Install Gatling, using the version appropriate for your system.

Note the path in which you installed it. You will need it in the next step.

Test that Gatling is compatible with your version of Java by running the following from the directory in which Gatling was installed. If you have a compatible Java, this will print the Gatling help message:

$ bin/gatling.sh --help
Copy
Upgrade your Java install if this fails and record the path to the new java for use in the next step.

2. Accounts
You will likely want to create bookmarks in your browser for the following services. As well, if you aren't using a password manager already, now's the time to get started. Finally, consider why you are not using 2FA. Each of these services supports 2FA which elevates the security of your account hugely.

2.1 Github
We will be using github.com in this course for a number of purposes:

Distribution of and/or grading of various homeworks (including the term project).
Collaboration with team members (including your term project).
Practicing the scrum methodology
Hosting of container images
Instruction:

If you do not have a GitHub account, create an account here.

Follow the instructions here for the command-line client. See here to configure your git for github.com with 2FA.

Sign up on Github Education. Start with 'Get benefits for students'.

Activate the Github Container Registry feature by following the instructions.
2.2 Docker & DockerHub
We will be using containers in this course to streamline development.

If you do not have a docker.com account already, create an account at docker.com. Note that this grants you access to both Docker.com and DockerHub, Docker's container registry service. Due to recent changes by DockerHub to throttle requests from free accounts, we will be using GitHub's new container registry feature instead to host our container images. (See here for more information.)

Create a personal access token (PAT) for your Github account. You will need the three scopes: read:packages, write:packages and delete:packages.

Configure your docker client to use GitHub Container Registry (ghcr.io) using this new token as follows:

$ export CR_PAT=<your-token>
$ echo $CR_PAT | docker login ghcr.io -u <your-github-id> --password-stdin
> Login Succeeded
Copy
2.3 Cloud Providers
Apply for course credits

Refer to Exercise 1A for details on applying for student credits. You will apply for all three sets of credits.

Configure your cloud CLIs

AWS: Refer here for instruction on configuring your environment to use the Starter account. The important note is that Starter account feature a session token which ages out. You will need to refresh this periodically if your account is idle (~1h of inactivity).

Microsoft Azure: Refer here for instruction to sign into Azure. The easiest is the interactive option (at the top of the page). Then set your defaults,

Google Cloud Platform: Set your GCP defaults with gcloud init.
Confirm your credits

AWS: Explore your starter account and locate the page that shows your credits. Screen grab the page showing your available credit.

Microsoft Azure: Explore your account and locate the page that shows your available credits. Start your navigation at the Azure Portal. Then find 'Subscriptions' (or navigate directly). Click on the entry 'Azure for Students'. You should find a link for "To check your remaining credit...". Navigate to this and screen grab the page showing your available credit.

Google Cloud Platform: Explore your account and locate the page that shows your available credits. Screen grab the page showing your available credit.
Submission
Create a PDF
Make a copy of the submission template(GDoc format).

Fill in:

a. The header box at the top of the document.

b. Content from the steps above.

Generate a PDF when you are done.

You must name your PDF according to the pattern: SFU-id-e1-submission.pdf where SFU-id is the portion of your email address preceding @sfu.ca. Unfortunately, you will be penalized for incorrect filename because of cascading dependencies for a large class.

A penalty will be assessed for failure to name your submission appropriately.

Canvas submission
Navigate to this exercise and upload the generated PDF.