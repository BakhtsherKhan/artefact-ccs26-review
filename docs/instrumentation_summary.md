# Sanitized Instrumentation Summary

This document summarizes the sender-side instrumentation used in the controlled experiments. It intentionally does not include executable Frida scripts, replay code, mutation code, or operational attack instructions.

## Purpose

The instrumentation was used to identify the sender-side materialization boundary where user-level message state is converted into row-level state before downstream delivery progression.

## Observed Boundary

The study focused on sender-side message materialization and storage behavior. The instrumentation observed fields such as message content, conversation identifier, message type, send status, direction flag, message identifier, and creation time.

## High-Level Workflow

The controlled analysis used three stages:

1. Observe normal message materialization.
2. Compare sender-side materialization with receiver-visible delivery.
3. Evaluate whether replayed materialized state, with or without freshness-related mutation, changes receiver-visible delivery behavior.

## Safety

The artifact does not include executable replay or mutation scripts. Operational code that could reproduce sender-side replay or message-state mutation is withheld to reduce misuse risk.

## Relation to Formal Models

The instrumentation motivates the CryptoVerif property tested in the paper: whether accepted receiver-side delivery is injectively bound to a unique preceding user-level send event.