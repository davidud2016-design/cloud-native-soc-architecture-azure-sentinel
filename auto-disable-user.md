# Playbook: Auto Disable Compromised User

## Trigger
Sentinel Incident Created

## Conditions
Severity = High  
Account Entity Present  

## Workflow

1. Extract Account Entity
2. Disable User in Azure AD
3. Add Comment to Incident
4. Notify SOC Team
5. Tag Incident as "User Disabled"

## Objective

Reduce Mean Time To Respond (MTTR) for identity-based compromise.
