# Map Network Drive Using Group Policy (GPO) Lab

## Lab Overview

A hands-on Windows Server 2022 lab focused on configuring and deploying mapped network drives using Group Policy Objects (GPO) within an Active Directory Domain Services (AD DS) environment. Practical experience was gained creating shared folders, configuring drive mappings, linking Group Policies to Organizational Units (OUs), managing user access, and verifying policy deployment on a domain-joined client computer.

## Objective

Configure Group Policy to automatically map a shared network drive for domain users when they log in.

## Environment

- **Platform:** Windows Server 2022 (`winserver2022`), Active Directory Domain Services (AD DS)
- **Domain:** `sudeep.local`
- **Client:** `Client01` VM
- **Tools used:** Group Policy Management, Active Directory Users and Computers, File Explorer, Shared Folders Management

## Procedure

1. **Create the GPO** — created a new Group Policy Object named `Map Finance Drive` in Group Policy Management.
2. **Configure drive map settings** — edited the GPO under User Configuration → Preferences → Windows Settings → Drive Maps, mapping the `F:` drive to the shared `CompanyData` folder.
3. **Link the GPO to the Finance OU** — linked `Map Finance Drive` to the `Finance` Organizational Unit under `sudeep.local`, so any user in that OU receives the `F:` drive mapping at login.
4. **Verify OU membership** — confirmed David Lee is a member of the Finance OU, so the policy applies to him; moved Sarah Wilson to the HR OU to confirm scoping is OU-specific.
5. **Share the target folder** — configured sharing permissions on the `CompanyData` folder so domain users can access it.
6. **Apply and test** — ran `gpupdate /force` to push the policy, then logged in as David Lee on the `Client01` VM and confirmed the `F:` drive mapping applied automatically.

## Topics Covered

- Creating a new Group Policy Object (GPO)
- Configuring Drive Maps in User Configuration Preferences
- Linking a GPO to an Organizational Unit
- Verifying GPO inheritance in Active Directory
- Moving users between Organizational Units
- Sharing folders and setting permissions for domain users
- Testing GPO application on a client VM
- Using `gpupdate /force` to apply policies

## Conclusion

Successfully used Group Policy Management to automatically map a network drive for domain users in a specific Organizational Unit. By creating and linking the `Map Finance Drive` GPO to the Finance OU, all users in that OU receive an `F:` drive mapping at login without manual configuration — verified end-to-end with David Lee's login on the `Client01` VM.

## Skills Demonstrated

GPO creation, drive map preference configuration, OU-based policy linking, folder sharing, Active Directory administration, and end-to-end policy testing on a domain-joined client VM.

## Full Documentation

[`Map Network Drive Using Group Policy (GPO) Lab of ADDS.pdf`](<./Map Network Drive Using Group Policy (GPO) Lab of ADDS.pdf>) contains the full step-by-step write-up with all implementation screenshots.

## Author

**Sudeep Kumar Chaurasiya**

Bachelor of Information Technology (Networking / Cyber Security)
Melbourne Institute of Technology, Sydney

GitHub: [github.com/sudeep0449](https://github.com/sudeep0449)
