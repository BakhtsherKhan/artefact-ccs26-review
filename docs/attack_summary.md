# Sanitized Attack Summary

This document summarizes the controlled replay-and-mutation experiment used in the paper. It intentionally does not include executable Frida scripts, replay code, mutation code, or operational instructions.

## Goal

The experiment evaluates whether one user-level send can lead to more than one accepted receiver-visible delivery in a server-mediated messaging system when the sender-side device is controlled by the adversary.

## Controlled Setting

The experiment was conducted in a closed laboratory environment using author-controlled devices, accounts, and network infrastructure. No third-party users, public traffic interception, or non-consensual data collection were involved.

## High-Level Method

The experiment examined the sender-side materialization boundary where user-level message state becomes row-level message state before downstream delivery progression.

The controlled tests compared:

1. normal message sending;
2. replay of a later sender-side transition;
3. replay of the early materialization boundary without mutation;
4. replay of the early materialization boundary with freshness-related mutation.

## Observed Outcome

The replay-only condition produced duplicate local sender-side state but did not produce duplicate receiver-visible delivery. The replay-plus-mutation condition produced duplicate receiver-visible delivery in the controlled experiment.

## Safety and Redaction

This artifact does not release executable replay or mutation scripts. It also excludes raw private logs, account identifiers, authentication material, and unsanitized screenshots.

## Relation to Formal Models

The experiment motivates the CryptoVerif model in which recovery and resumption legitimacy can hold while injective delivery correspondence fails. The fixed model restores injective delivery correspondence by enforcing freshness across sender, server, and receiver state.