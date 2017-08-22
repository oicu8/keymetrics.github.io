---
layout: docs
title: Keymetrics pricing FAQ
description: pricing FAQ
permalink: /docs/pages/pricing-faq
---

# Pricing and plan limitations FAQ

This page lists the frequently asked questions about the Keymetrics pricing system andthe specificity of our plan limitations.

# Process-based pricing

## What is a process?

A 'process' represents a system process, put simply each entry in `pm2 list` is a process.
It can be a worker in a cluster, a app in fork mode or a module.

### What about the cluster mode?

When you use the [cluster mode](http://pm2.keymetrics.io/docs/usage/cluster-mode/) (`pm2 start -i `) each instance will be counted as a process.
If you start 3 instances of the same application they will all count towards your process plan limit.

### Can I select which processes I want monitored?

Yes, you can use the command `pm2 unmonitor [APP_NAME|ID]` to stop monitoring a process via Keymetrics.
When using `pm2 ls` you should see a red dot indicating the application will not be followed by Keymetrics.

If you want to monitor the process again use `pm2 monitor [APP_NAME|ID]`.

## What is a server?

A 'server' represents one linked PM2 instance. Normally, each bare metal server/container/VM have one PM2 instance.

# Notification limit system

For some specific plans you have a limited number of reporting avalaible for a certain period. This is listed in the plan specifications.
After your notifications are used you will receive a mail warning you that you will receive no more mails until the next reset

For example the Garage plan lets you have 10 total notifications per day, and resets every day. 

## When does the notification limitation reset?

The counter resets every day at midnight at GMT+1.

## What happens to the notification limit when I upgrade?

When you upgrade the notification counter will be reset.

## What happens to the notification counter when I downgrade?

When you downgrade the notification reset will not be reset to prevent abuse.
If you are over your current plan limit you will have to wait for the reset.