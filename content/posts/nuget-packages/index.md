---
title: 'NuGet Packages'
date: 2020-05-02 21:07:09 +01:00
layout: post
permalink: /2020/05/nuget-packages/
categories:
    - dotnet
tags:
    - dotnet
---

I can never remember how to limit what versions of NuGet packages are allowed for a project. So here are how it’s done

## Version ranges and wildcards

When referring to package dependencies, NuGet supports using interval notation for specifying version ranges, summarized as follows:

| Notation | Applied rule | Description |
|---|---|---|
| 1.0 | x ≥ 1.0 | Minimum version, inclusive |
| (1.0,) | x &gt; 1.0 | Minimum version, exclusive |
| \[1.0\] | x == 1.0 | Exact version match |
| (,1.0\] | x ≤ 1.0 | Maximum version, inclusive |
| (,1.0) | x &lt; 1.0 | Maximum version, exclusive |
| \[1.0,2.0\] | 1.0 ≤ x ≤ 2.0 | Exact range, inclusive |
| (1.0,2.0) | 1.0 &lt; x &lt; 2.0 | Exact range, exclusive |
| \[1.0,2.0) | 1.0 ≤ x &lt; 2.0 | Mixed inclusive minimum and exclusive maximum version |
| (1.0) | invalid | invalid |

