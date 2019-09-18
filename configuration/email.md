# Email Setup
Magento ships with an email module by default.

## Configuration Steps
All the following are in `Stores -> Configuration` in the admin panel

#### General -> Store Email Addresses

Change the emails to `no-reply@domain.com` where domain.com is your domain

#### Advanced -> System -> Mail Sending Settings
```
Disable Email Communications = No
Host=Use system value
Port=Use system value
Set Return-Path=No
