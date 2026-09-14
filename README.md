# Java Parallel Web Crawler

A Java-based parallel web crawler that fetches and processes web pages concurrently. The project demonstrates Java concurrency, thread-safe synchronization, dynamic proxies, dependency injection, profiling, JSON processing, and functional programming with the Stream API.

## Overview

The Parallel Web Crawler crawls real web pages and extracts information from them while respecting a configured crawl timeout and maximum crawl depth.

The project provides both sequential and parallel crawling implementations. The parallel implementation uses Java's `ForkJoinPool` framework to process multiple pages concurrently while safely tracking URLs that have already been visited.

## Key Features

- Parallel web-page crawling
- Sequential web crawler implementation
- Real web-page crawling
- Configurable crawl timeout
- Maximum crawl depth
- Thread-safe URL tracking
- Dynamic proxy-based performance profiling
- JSON configuration loading
- JSON result generation
- Word frequency analysis
- Dependency injection using Guice
- Automated unit testing

## Technologies

- Java 17
- Maven
- Guice
- JSoup
- JUnit
- ForkJoinPool
- RecursiveAction
- ConcurrentHashMap
- ConcurrentSkipListSet
- Java Reflection API
- Dynamic Proxy
- Java Stream API
- JSON

## Architecture

The application uses a strategy-based design to support different crawler implementations.

```text
                    WebCrawler
                       |
              +--------+--------+
              |                 |
              v                 v
   SequentialWebCrawler   ParallelWebCrawler
                                |
                                v
                         ForkJoinPool
                                |
                         RecursiveAction
                                |
                 +--------------+--------------+
                 |                             |
           Page Processing              URL Synchronization
