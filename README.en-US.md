# ADRs

Architectural Decision Records or simply ADRs, are documents that record important decisions involving the "lifecycle" of the software or project, such as which programming language was chosen, which configuration management tool, whether to use containers or not, among other records that we deem useful to be documented for the prosperity of the project and/or the company.

We often come across projects in progress and ask to ourselves: who chose this tool? Who chose that language? Don't they know  they could have solved it this other, much simpler way? When this happens we are indignant because for us the advantage of X over Y is very clear and it is absurd they would not have done otherwise. The point is, we don't always know the whole context, the reasons that led to adopt that strategy or the project's restrictions both in technology and in infrastructure for example. There is always a context to be observed and the ADRs give us this context at times when the people who started the project do not always remain in the company, or even we no longer remember why we did it that way.

We usually use text files (in this case we are using __markdown__ format files) and keep them with the project, or even in a centralized documentation project, when these decisions address company standards and not just a specific project or application. These files are usually short and describe what the decision was made in commonly having the following sections:

* Title or name of the ADR, what it is about
* Context, talking about the problem, variables involved, project restrictions, costs, everything that is pertinent to contextualize the description.
* Decision, describing which approach was chosen
* Status, indicating whether it is accepted, deprecated or just proposed
* Consequences, showing what should be expected from that decision, showing positives and negatives of the chosen approach

We can enhance ADRs by adding options that were considered but not accepted as a solution, along with their strengths and weaknesses.

__But what should we have ADRs for?__

We can document as ADR any type of decisions, but to reduce the amount and increase the speed of delivery, we do not document everything, just definitions of standards used and tools, such as using a message broker like RabbitMQ or a Redis PubSub for example.

Standard language items, such as variable name patterns, where each language has its own pattern, are usually not documented, it is believed in the team's common sense that we don't need to document in such detail at this point.


## Tools

To help with the generation and management of ADRs, we can use tools, in the case of CLIs for this, there are two suggestions that are interesting:

* [Command-line tools for working with Architecture Decision Records](https://github.com/npryce/adr-tools)
* [Command line tools with python by Victor Sluiter](https://bitbucket.org/tinkerer_/adr-tools-python/src/master/)

## Templates and examples

This project contains templates and examples to help you produce your own ADRs. Each of the examples was assembled in a different template, already to demonstrate in the real world, how to use each one of the templates, some more detailed, others more objective, but all aim to record the history of decisions involving the software or project.

Here are the credits below where the templates were found:

* [Template](https://github.com/joelparkerhenderson/architecture-decision-record/blob/main/templates/decision-record-template-madr/index.md) by MADR
* [Template](https://github.com/joelparkerhenderson/architecture-decision-record/blob/main/templates/decision-record-template-by-michael-nygard/index.md) by Michael Nygard
* [Template](https://github.com/joelparkerhenderson/architecture-decision-record/blob/main/templates/decision-record-template-by-jeff-tyree-and-art-akerman/index.md) by Jeff Tyree and Art Akerman
* [Template](https://github.com/pmerson/ADR-template) by Paulo Merson