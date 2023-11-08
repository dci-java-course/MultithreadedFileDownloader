# Objective: 

Create a Java program that allows users to download web pages using multiple threads, handle exceptions, and save the web page content to files.

Input: Allow the user to provide a list of URLs to download and specify the number of threads to use for downloading.

Multithreading: Create and manage multiple threads, each responsible for downloading a specific file from the list of URLs.

Download Progress: Display the download progress for each file, including the percentage of completion.

Exception Handling: Implement proper error handling to deal with exceptions such as invalid URLs, network errors, or file access issues. Log any exceptions that occur.

Save Files: Save the downloaded files to a specified directory on the local machine.


# Features:

input: Allow the user to input a list of URLs to download web pages from.

Multithreading: Create multiple threads to concurrently download web pages from the list of URLs.

Exception Handling: Implement proper error handling to deal with exceptions, such as network errors or invalid URLs.

Save Web Pages: Save the downloaded web page content to individual text files.

# Project Structure:

Here's a simplified structure for the project:

WebPageDownloader.java: The main class that manages the downloading process and user interaction.

DownloadTask.java: A class representing a download task that can be executed by a thread.

FileWriter.java: A utility class for saving web page content to text files.

Main.java: The entry point of the application.

# Guidelines
1.User Input and Threads:
Accept a list of URLs to download web pages from.//using arraylist
provide the number of threads to use for downloading.
Use ExecutorService to manage threads.

2.Download Task (DownloadTask):
Create a DownloadTask class that implements the Callable interface.
Each DownloadTask should download a web page content from a URL.
Properly handle exceptions during download.

3.Web Page Download:
Use the URL and URLConnection classes to download web page content.
Store the content temporarily in a String or a StringBuilder.

4.File Saving:
Implement a FileWriter class to save web page content to text files.
Derive a filename from the URL by extracting the last part (after the last /) and append ".txt" for the file extension.

5.Exception Handling:
Catch and handle exceptions, such as network errors or invalid URLs.

