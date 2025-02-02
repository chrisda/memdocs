---
title: Support for the Windows ADK
titleSuffix: Configuration Manager
description: Learn about the Windows Assessment and Deployment Kit (ADK) versions that are supported for OS deployment with Configuration Manager.
ms.date: 03/28/2024
ms.subservice: core-infra
ms.service: configuration-manager
ms.topic: conceptual
author: PalikaSingh
ms.author: palsi
manager: apoorvseth
ms.localizationpriority: medium
ms.collection: tier3
ms.reviewer: mstewart,aaroncz 
---

# Support for the Windows ADK in Configuration Manager

*Applies to: Configuration Manager (current branch)*

When you deploy operating systems with Configuration Manager, the Windows Assessment and Deployment Kit (ADK) is a required external dependency. For more information, see the following articles:

- [Infrastructure requirements for OS deployment](../../../osd/plan-design/infrastructure-requirements-for-operating-system-deployment.md#windows-adk)

- [Download the Windows ADK](/windows-hardware/get-started/adk-install)

    > [!IMPORTANT]
    > ADK for Windows 11, Version 22H2 and all earlier supported versions of Windows 10 and 11 (Updated September 2023 - version 10.1.25398.1) is required to deploy Windows 10/11 ARM64 operating system deployment.
    > 
    > Windows PE is a separate installer. Make sure to download both the **Windows ADK** and the **Windows PE add-on for the ADK**.
        
    > [!Note]
    > ADK for Windows 11, version 22H2 (updated September 2023): VBScript is not currently working in WinPE. It is expected to be fixed in an upcoming servicing update.
      

## Windows ADK versions

The following table lists the versions of the Windows ADK that you can use with different versions of Configuration Manager.

| Windows ADK version            | ConfigMgr 2211| ConfigMgr 2303 | ConfigMgr 2309 | ConfigMgr 2403  |
|--------------------------------|----------------|----------------|----------------|----------------|
| **Windows 11**<br>(10.1.22621.1)| ![Supported](media/green-check.png) | ![Supported](media/green-check.png) | ![Supported](media/green-check.png)| ![Supported](media/green-check.png) |
| **Windows 11**<br>(10.1.22000) | ![Supported](media/green-check.png) | ![Supported](media/green-check.png) | ![Supported](media/green-check.png)| ![Supported](media/green-check.png) |
| **Windows Server 2022**<br>(10.1.20348)  | ![Supported](media/green-check.png) | ![Supported](media/green-check.png) |![Supported](media/green-check.png)|![Supported](media/green-check.png) |
| **Windows 10, version 2004**<br>(10.1.19041)| ![Supported](media/green-check.png) | ![Supported](media/green-check.png) | ![Supported](media/green-check.png) |![Supported](media/green-check.png) |
 
|Key|
|--|
| ![Supported](media/green-check.png) = **Supported** <br/> This table only shows Windows ADK supportability in relation to the version of Configuration Manager. Microsoft recommends using the Windows ADK that matches the version of Windows you're deploying. Use the latest Windows ADK version when deploying the latest Windows version. The latest Windows ADK version may support deployment of older OS versions, such as Windows 8.1.<!-- SCCMDocs issue 1229 --> For more information on Windows ADK component supportability, see [DISM supported platforms](/windows-hardware/manufacture/desktop/dism-supported-platforms), [USMT requirements](/windows/deployment/usmt/usmt-requirements#bkmk-1), and [Choose the right ADK for your scenario](/windows-hardware/get-started/adk-install#choose-the-right-adk-for-your-scenario). |
| ![Backwards compatible](media/blue-compat.png)  = **Backward compatible** <br/> This combination isn't tested but should work. We'll document any known issues or caveats. |
| ![Not supported](media/red-x.png) = **Not supported** |

## Support notes

- Configuration Manager only supports x86, amd64 and arm64 components of the Windows ADK. 

- Windows Server builds have the same Windows ADK requirement as the associated Windows client version. For example, Windows Server 2016 is the same build version as Windows 10 LTSB 2016.

- If you're deploying both Windows 11 and Windows Server 2022, use the Windows ADK for Windows 11, which is the latest version. If you're deploying Windows Server 2022 and not Windows 11, you can use either Windows ADK for Windows Server 2022 or Windows 11.

<!--12440724-->
[!INCLUDE [windows11-adk-x86](includes/windows11-adk-x86.md)]

## Known issues

<!-- 11307733 -->
[!INCLUDE [windows-adk-11-preprovision-bitlocker](includes/windows-adk-11-preprovision-bitlocker.md)]

## Next steps

[Support for Windows 11](support-for-windows-11.md)

[Support for Windows 10](support-for-windows-10.md)

[Supported OS versions for clients](supported-operating-systems-for-clients-and-devices.md)
