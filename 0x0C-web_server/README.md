# Web Servers

## Introduction

This repository contains basic information about web servers, child processes, HTTP requests, and the Domain Name System (DNS). It's designed to help beginners understand these fundamental concepts in web development and networking.

## Table of Contents

- [What is the main role of a web server?](#what-is-the-main-role-of-a-web-server)
- [What is a child process?](#what-is-a-child-process)
- [Why web servers usually have a parent process and child processes?](#why-web-servers-usually-have-a-parent-process-and-child-processes)
- [What are the main HTTP requests?](#what-are-the-main-http-requests)
- [What is DNS?](#what-is-dns)
- [What is DNS main role?](#what-is-dns-main-role)
- [DNS Record Types](#dns-record-types)

## What is the main role of a web server?

A web server is like a librarian for the internet. When you type a website's address into your browser, the web server finds the website's files and sends them to your computer so you can see the website.

## What is a child process?

A child process is a separate task that is created by a parent process to do specific work. In computing, it's like having a manager (parent process) who oversees multiple workers (child processes) in a restaurant.

## Why web servers usually have a parent process and child processes?

Web servers often use a parent process to manage multiple child processes. This is like having a manager (parent process) who oversees multiple workers (child processes) in a restaurant. The manager can assign tasks to the workers, monitor their progress, and ensure that the restaurant runs smoothly.

## What are the main HTTP requests?

- **GET**: Asking for a book from the library.
- **POST**: Submitting a form to a website.
- **PUT**: Updating a book's information in the library.
- **DELETE**: Removing a book from the library.

## What is DNS?

DNS stands for Domain Name System. It's like a phone book for the internet. When you type a website's name into your browser, DNS helps find the website's address (IP address) so your browser can load the website.

## What is DNS main role?

DNS's main role is to translate human-friendly website names into IP addresses that computers can understand. It's like a translator for the internet.

## DNS Record Types

- **A Record**: Tells you the IP address of a website.
- **CNAME Record**: An alias for another website.
- **TXT Record**: Can hold any text information, often used for verification purposes.
- **MX Record**: Tells you where to send emails for a domain.

## Examples

- **A Record Example**: `google.com A 172.217.12.142`
- **CNAME Record Example**: `www.example.com CNAME example.com`
- **TXT Record Example**: `example.com TXT "google-site-verification=abc123"`
- **MX Record Example**: `example.com MX mail.example.com`

## Conclusion

Understanding these basic concepts is crucial for anyone interested in web development and networking. This repository aims to provide a simple and clear overview to help beginners get started.

![Web Servers and Networking Basics](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-sysadmin_devops/266/8Gu52Qv.png)
