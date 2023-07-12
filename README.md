# sig_generator
Email Signature Generator
Python script for generating email signatures from a single (HTML) template for all employees at once


## What it does

It reliefs you from the burden of manually editing large numbers of email signatures to update company, event, or employee information. Instead you update the information in the [data set][data-set], the design of the [template][template], and let the [script][script] generate the HTML signatures for all your employees.

    data set
        +    -> script -> signatures
    template

The included template is kept simple as it merily aims to show which placeholders can be used. Use an individual signature design by adding placeholders and renaming it to `signature.template.html`.


### Use cases

This is the right tool for you, if a large number of employee email signatures have to be updated.
The more often this happens, the more employees the company has, and the more information has to be changed in each signature, the more useful this tool will be for you.

Typical reasons for updating many email signatures at once:
* Announcements, e.g. trade fairs or special offers.
* Update of basic company information, e.g. company or department relocation, new CEO, company logo, or social media accounts.
* The marketing department likes to continuously tweak the design of the signature.


### Key features

* *Reuse of information*  
Once information was entered in one section of the configuration it can be reused in any other section, e.g. a department's name and telephone number can be referenced for all employees of that department.

* *Optional free text*  
Feel free to add role or employee specific text to all or selected signatures, e.g. the rates for calling the support team to the signatures of all support team members.

* *Optional line with mobile phone number*  
Add a mobile phone number to records of people that have one and omit it for those who don't. The respective line will only be present in the signature of those employees, that actually have a mobile.


### Available input fields

The following fields are customizable via the data set.
Additional information such as an email disclaimer statement is best written directly into the template.

* Company: company name, street, city, state, zip code, telephone, website, top executives, local court
* Employee: first name, last name, department, telephone, mobile, fax, email, additional free form text


## Getting started

```bash
$ ./generate.py
```

It requires Python v3.2 or later.

When you execute the script, it reads the data file with the company's and every person's contact details as well as the HTML signature template file. The HTML template defines the design of the final HTML signatures and contains placeholders for information stored in the data file. The script then replaces all placeholders with the company's and a person's respective information and saves the resulting HTML signature files to the `output` folder.

The data file uses an extended `.ini` format.
