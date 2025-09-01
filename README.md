# Bing-URL-Submitter 🌐
![screenshot](/webmaster-0.png)

## About...

### The script is used to submit URLs to Bing Webmasters Tools from command-line.

After providing the appropriate parameters (address of the website verified in Webmasters Tools, name/path to the sitemap, unique API token), the script **downloads the indicated sitemap file**, **parses it**, extracting the addresses to be sent from it, and then **creates a JSON query along with the addresses** and the API token and **sends it to Bing Webmasters**.

The program is intended to **help send information about URLs, pages and subpages of websites to Bing**, which in turn will help build the **website's SEO** in Bing browser.

Describing the principle of its operation in more detail, we can say that the "webmaster" downloads, parses and then sends the number of addresses provided by the user (by default **100**, because Bing assigns so many submits per day to new Webmasters Tools users), **saving them to his cache file** so that when it restarts **addresses already sent have not been sent again**.

It is possible to create a **service script** instance that will **automatically submit** subsequent URLs in the background **without additional user intervention**.

The script works without problems with the **sitemap txt** file and simple non-recursive **sitemap xml** files.

> [!NOTE]
> In the case of **recursive sitemaps**, you must run the script multiple times defining the appropriate sitemap file paths.

![screenshot](/webmaster-3.png)

### There are 3 versions of the script available.

The "**webmaster**" script contains thematic decorations (ASCII logo, appropriate coloring) and a more readably formatted response from bing.

In turn, "**webmaster-text**" and "**webmaster-text-pl**" contain almost no formatting, do not display the ASCII logo, do not contain coloring, and the response from Bing is displayed in JSON format.

The "**webmaster-text**" script has descriptions, help and error messages written in English, while "**webmaster-text-pl**" is displayed in Polish.

### The project is fully a shell script.

All "**webmaster**" scripts use the built-in commands **bash**, **coreutils**/**busybox** and **cur**l, **xargs**, **grep**.

All required packages **are easy to install** using apt, rpm, etc. and do not require adding additional repositories.

## Instalation ...
```
git clone https://github.com/BuriXon-code/Bing-URL-Submitter
cd Bing-URL-Submitter
chmod +x webmaster*
```

![screenshot](/webmaster-1.png)

## Help and options ...
```
./webmaster -h
```
or
```
./webmaster --help
```

## Usage examples ...
### 1. Placing parameters in the command-line:
```
./webmaster -u "https://your-webside.com/" -n "sitemap.xml" -t "yourAPItoken" -c 100
```
> [!WARNING]
> The URL you provide is required to contain the **http://** or **https://** prefix.
> 
> You can obtain the **API token** in the **Webmasters Tools management panel**.

> [!NOTE]
> Parameter -c | --count is **not required** (set to **100** by default).

### 2. Using a file containing data.
```
./webmaster -f /path/to/file
```
### Sample file content:
```
url address
API token
sitemap name/location
```

> [!WARNING]
> The file **must** contain parameters in the **correct immutable order**!

### 3. Using enviroment variables.
```
./webmaster -e
```
> [!NOTE]
> Environment variables **must** be defined in **advance**. The script looks for the variables **$SUBMIT_URL**, **$SUBMIT_SITEMAP**, **$SUBMIT_API**.

### Defining variables:
```
export SUBMIT_URL="url address"
export SUBMIT_SITEMAP="sitemap name/location"
export SUBMIT_API="API token"
```
> [!NOTE]
> Variable definitions **can be written into the shell configuration file** to be exported automatically every time the terminal is launched.

## Compatibility ...

The script is compatible with **Unix systems based on coreutils/busybox**, equipped with **bash**, with **curl** and **xargs** installed.

The script was tested with sitemaps containing from 10 to 15,000 URLs.

It was tested on Kali 2024.2, Ubuntu 22.04, Ubuntu 24.04, Termux 0.119-beta.

![screenshot](/webmaster-2.png)

## Support
### Contact me:
For any issues, suggestions, or questions, reach out via:

- *Email:* support@burixon.dev  
- *Contact form:* [Click here](https://burixon.dev/contact/)
- *Bug reports:* [Click here](https://burixon.dev/bugreport/)

### Support me:
If you find this script useful, consider supporting my work by making a donation:

[**Donations**](https://burixon.dev/donate/)

Your contributions help in developing new projects and improving existing tools!




