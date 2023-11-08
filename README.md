# Objective: 

Create a Java program that allows users to download web pages using multiple threads, handle exceptions, and save the web page content to files.

Input: Allow the user to provide a list of URLs to download and specify the number of threads to use for downloading.

Multithreading: Create and manage multiple threads, each responsible for downloading a specific file from the list of URLs.

Download Progress: Display the download progress for each file, including the percentage of completion.

Exception Handling: Implement proper error handling to deal with exceptions such as invalid URLs, network errors, or file access issues. Log any exceptions that occur.

Save Files: Save the downloaded files to a specified directory on the local machine.


# Project Structure:

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
