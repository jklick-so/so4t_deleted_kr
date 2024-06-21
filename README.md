# Deleted User Knowledge Reuse Report for Stack Overflow for Teams
A Python script that uses the Stack Overflow for Teams API to generate a report to measure the reuse of knowledge generated by users who have left the organization.

## Table of Contents
* [Requirements](https://github.com/jklick-so/so4t_deleted_kr?tab=readme-ov-file#requirements)
* [Setup](https://github.com/jklick-so/so4t_deleted_kr?tab=readme-ov-file#setup)
* [Usage](https://github.com/jklick-so/so4t_deleted_kr?tab=readme-ov-file#usage)
* [Support, security, and legal](https://github.com/jklick-so/so4t_deleted_kr?tab=readme-ov-file#support-security-and-legal)


## Requirements
* Stack Overflow Enterprise or Business
* Python 3.8 or higher ([download](https://www.python.org/downloads/))
* Operating system: Linux, MacOS, or Windows

## Setup

[Download](https://github.com/jklick-so/so4t_deleted_kr/archive/refs/heads/main.zip) and unpack the contents of this repository

**Installing Dependencies**

* Open a terminal window (or, for Windows, a command prompt)
* Navigate to the directory where you unpacked the files
* Install the dependencies:
```sh
python3 -m pip install -r requirements.txt --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org
```

> NOTE: Depending on your installation of Python, you may need to use `python` or `py` instead of `python3` in the command above. If `python3` is not a recognized command, you can check which command to use by running `python --version` or `py --version` in your terminal and seeing which responds with the installed Python version.


**API Authentication**

To authenticate with the Stack Overflow API, you will need to generate a valid access token. If you're using Stack Overflow Enterprise, you'll also need an API key.

* For Basic or Business, instructions for creating a personal access token (PAT) can be found in [this KB article](https://stackoverflow.help/en/articles/4385859-stack-overflow-for-teams-api).
* For Enterprise:
    * Creating a key can be done by logging in to Stack Overflow Enterprise and visiting your user profile page > Settings > API applications. This is also a preliminary step to generating an API token.
    * A token can be created by following the instructions in the KB article titled [Secure API Token Generation Using OAuth with PKCE](https://support.stackenterprise.co/support/solutions/articles/22000286119-secure-api-token-generation-using-oauth-with-pkce)


## Usage

In a terminal window, navigate to the directory where you unpacked the script. Run the script with the following format:

```sh
python3 main.py
```

* At the beginning of the script, you'll be prompted for the URL of your Stack Overflow for Teams instance and your API token. 
* If you're using Stack Overflow Enterprise, you'll also be prompted for your API key. 
* Lastly, you'll be prompted for a proxy URL. If you don't require this -- or you're not sure -- just leave it blank and hit enter.

**Storing the API connection information as environment variables**

Optionally, you can avoid repeatedly typing the URL, token, key, and proxy settings by storing them as environment variables ([MacOS](https://apple.stackexchange.com/questions/106778/how-do-i-set-environment-variables-on-os-x) | [Windows](https://superuser.com/questions/212150/how-to-set-env-variable-in-windows-cmd-line)). This is especially useful if you'll be using the script frequently. If you choose to do so, here are the names of the environment variables that the script will look for:

* `SO_URL` - URL of your Stack Overflow for Teams instance (required)
* `SO_TOKEN` - API token (required)
* `SO_KEY` - API key, if using Enterprise   
* `SO_PROXY` - Proxy URL, if needed

As a potentially easier option, you can also create a file named `.env` and store it in the same directory as the Python script. The contents of that file should look like this:
```
SO_URL=https://YOUR.INSTANCE.URL/
SO_TOKEN="YOUR_TOKEN>"
SO_KEY="YOUR_KEY" # only needed for Enterprise
SO_PROXY="PROXY_URL"  # optional, if you need to use a proxy server
```

## Support, security, and legal
Disclaimer: this project is a labor of love that comes with no formal support from Stack Overflow. 

If you run into issues using the script, please [open an issue](https://github.com/jklick-so/so4t_deleted_kr/issues). You are also welcome to edit the script to suit your needs, steal the code, or do whatever you want with it. It is provided as-is, with no warranty or guarantee of any kind. If the creator wasn't so lazy, there would likely be an MIT license file included.
