---
author: cbhl
date: '2010-06-18 07:10:26'
layout: post
slug: sso-nfs-homedirs-part-1a-dns-for-my-home-network
status: publish
title: 'SSO & NFS Homedirs Part 1a: DNS for my Home Network'
wordpress_id: '54'
categories:
- Thought Dump
---

This post is incomplete, but I didn't want it sitting around as a draft
any longer. Well, it has been over a month since I started my co-op job.
I'm writing this post from the iPad that I get intermittent access to at
work, using the official Wordpress app for iPhone OS devices. Typing
with the device in the vertical orientation is pretty much impossible
for someone who is used to touch typing on a standard 104 key keyboard,
and while the keys in the horizontal mode are more-or-less the same size
as those on a regular apple keyboard, I still manage to make a mess of
typing on it. If I actually get myself one of these for personal and/or
school use, I'm going to need to get a real apple Bluetooth keyboard to
go with it. Ubuntu 10.04 LTS has been out now for ages, and I've been
putting off the upgrade at home because I wanted to get Single Sign On
(SSO) and centralized home directories working before the upgrade. I had
this all half working at one point or another, but during the last
upgrade I got frustrated and lazy and made copies of the passwd and
shadow files, which was messy and evil and only worked because my family
doesn't change their passwords very often. I'd like to do it right for
once. (Off topic: is it just me, or does this wordpress app not support
copy and paste?) So the first part of getting set up is trivial; ubuntu
is already installed on the home server. Basic essentials include
ubuntu-standard, language-pack-en, ntp. I figure I should actually give
it a nice dynamic domain name, and so I set off setting up BIND on my
VPS. Then I go to netfirms' website, thinking I'll just delegate a
subdomain to my VPS. Well, my support ticket for that is still open and
not going anywhere, so alas I fork over some money and register a new
domain name for my home network. For the sake of being contrary, I also
decide to get secondary DNS from DynDNS. (Why is their custom DNS
solution cheaper?) Configure the new zone in BIND, setting low TTL for
now. Update NS records for ipv4 first, adding the glue record at net
firms. This is listed as a custom nameserver and only works for ipv4
from what I can see. Set up basic A and AAAA records. Now the fun
part... Dynamic DNS. Set up dns keys, acls, and dhcpd. Voilà. Now ipv6,
shore wall. We're moving offices at work this weekend, so I won't have
time to update this post for a week or so.
