# Quick Start

> If you want to get started really quickly, you can follow this quick start tutorial and create a simple OER within just a few minutes.

## 1. Create a GitHub account, if you don't have one yet
> As we will host our OER on [GitHub](https://github.com/), a free GitHub account is required.

If you do not have an account yet, go to GitHub's sign up page and create a free account: [https://github.com/signup](https://github.com/signup).

Afterwards, log into your account.

## 2. Create your project
> Create the place where your OER lies.

Go to the [Markdown Documents Template](https://github.com/TIBHannover/markdown-documents-template) and click on the green **Use this template** button, then on **Create a new repository**. This generated your own project (called `repository`).
Assign the repository's owner to yourself (or to a group of your choice, if you are a member of one) and give it a short, but meaningful name that describes your OER. This name will also be the used for the URL to your OER. Optionally add a description.
Make sure that the repository is set to **public**.
Lastly, confirm by clicking on **Create repository from template**.

<video width="100%" src="_static/videos/create-from-template.mp4" controls></video>

## 3. Fill the project with your content

> Now that you have your own project/repository, you can fill it with your own content.

Currently, you have the template's dummy data in your repository. You can edit a file by clicking on the file and then on the edit button. The files you should edit are:

* `chapter01.md`
* `chapter02.md`
* `chapter03.md`
* `chapter04.md`

You can start by edititing `chapter01.md`. Click on the file, the in the top right corner, click on the pen symbol ("Edit this file"). You can delete the file's content and start writing something of your own.

Now, in the top right corner, click on the green "Commit changes..." button. Write a short message on what you have changed ("Commit message"), if you want a longer description, and now click on the green "Commit changes" button.

You can also choose to create or delete files. If you do not want the four chapter files that were created by the template, you can click on the file, click on the three dots on the top right of the file, and then on "Delete file". To upload files, you can click on the "Add file" button in your repository.

## 4. Generate the OER
> The automatic generation will take your content and generate different output formats.

Lastly, enable the automatic generation of your OER. To do this, go to the project's `Settings` -> `Pages` and in `Build and Development` set the source to `GitHub Actions`. After this, you can head to the `Actions` tab and click on the newest workflow run. If the worklow already ran, you will find that it failed. This happened because the Pages were not enabled yet. In this case, click on re-run jobs. Otherwise, wait until the jobs have finished. The generated documents are now created.

<video width="100%" src="_static/videos/pages.mp4" controls></video>

## 5. Add your metadata
Go to our [Metadata Generator](https://oersi.gitlab.io/metadata-form/metadata-generator.html) and insert the metadata that describes your OER. In the top right corner, you have the option to switch the language between **German** ("DE") and **English** ("EN").

Once you are done, click on the "Generate" button in the bottom of the page. The metadata is now generated in a format our template understands. Now copy everything to your clipboard. For this, you can click on "Copy".

In your repository, click on the `metadata.yml` file and then on the pen symbol ("Edit this file") to edit the file. Delete the file's contents and paste the metadata from your clipboard. Now click on the green "Commit changes..." button and confirm with "Commit changes".

Now at the bottom of the page, you can click on `Generate`. This generates the metadata in the correct format. You can then copy the output to your clipboard either by using the `Copy` button, or by selecting the whole text (`Ctrl + A`) and copying it (`Ctrl + C`).

<video width="100%" src="_static/videos/metadata-placeholder.mp4" controls></video>

## Done!
At the front page of your repository, inside the `README.md` content, there are several links you can use to view your generated documents. Click on the `landing page` link to view a page that lists metadata about your OER and supplies several links to different output formats (like a web version, a pdf version, ...).

> To insert your OER into the OER search index [oersi.org](https://oersi.org), head to the `About` section in the index of your repository, click on the settings symbol and add `open-educational-resources` to `Topics`. Your course will be indexed at night and appear on the next day.