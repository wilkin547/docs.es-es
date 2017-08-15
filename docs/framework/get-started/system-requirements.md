---
title: Requisitos de sistema de .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- software requirements
- .NET Framework, system requirements
- system requirements
- operating systems supported
- hardware requirements
ms.assetid: 298275e2-da1d-4618-9f74-6a3567832350
caps.latest.revision: 95
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: 18875105836ee4be0a3d3fb61a83ef6cd29b8c58
ms.contentlocale: es-es
ms.lasthandoff: 08/05/2017

---

# <a name="net-framework-system-requirements"></a>Requisitos de sistema de .NET Framework

En las tablas de este tema se indican los requisitos de hardware, sistema operativo y software de .NET Framework 4.5 y de sus versiones secundarias (4.5.1 y 4.5.2), de [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y sus versiones secundarias (4.6.1 y 4.6.2) y de .NET Framework 4.7. Los entornos de desarrollo que permiten desarrollar aplicaciones para .NET Framework tienen otros requisitos diferentes.

Para obtener información y vínculos de descarga, vea [Instalar .NET Framework para desarrolladores](../../../docs/framework/install/guide-for-developers.md).

Para obtener información sobre el ciclo de vida de soporte técnico de las versiones de .NET Framework, vea [Microsoft Support Lifecycle](https://support.microsoft.com/en-us/lifecycle/search?sort=PN&alpha=Microsoft%20.NET%20Framework&Filter=FilterNO).

## <a name="hardware-requirements"></a>Requisitos de hardware

|                          |        |
| ------------------------ | ------ |
| **Procesador**            | 1 GHz  |
| **RAM**                  | 512 MB |
| **Espacio en disco (mínimo)** |        |
| 32 bits                   | 4.5 GB |
| 64 bits                   | 4.5 GB |

## <a name="installation-requirements"></a>Requisitos de instalación

Necesita tener privilegios de administrador para poder instalar .NET Framework. Si no tiene derechos de administrador en el equipo en el que quiere instalar .NET Framework, póngase en contacto con el administrador de red.

## <a name="supported-client-operating-systems"></a>Sistemas operativos de cliente admitidos

| Sistema operativo | Ediciones compatibles | Preinstalado con el sistema operativo | Instalable por separado |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows 10 Creators Update | 32 bits y 64 bits | .NET Framework 4.7 | | 
| Actualización de aniversario de Windows 10 | 32 bits y 64 bits | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|.NET Framework 4.7 |
| Actualización de noviembre de Windows 10 | 32 bits y 64 bits | [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] | |
| Windows 10  | 32 bits y 64 bits | [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] | [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] |
| [!INCLUDE[win81](../../../includes/win81-md.md)] | 32 bits, 64 bits y ARM | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7 |
| [!INCLUDE[win8](../../../includes/win8-md.md)] | 32 bits, 64 bits y ARM | [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] |
| Windows 7 SP1|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7 |
| Windows Vista SP2|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] |
| Windows XP |32 bits y 64 bits | -- | .NET Framework 4 |

 **Notas:**

- Para sistemas de Windows 7, tenga en cuenta que .NET Framework requiere Windows 7 SP1. Si usa Windows 7 y aún no ha instalado Service Pack 1, deberá hacerlo antes de instalar .NET Framework.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] se admite en el entorno de preinstalación de Windows (Windows PE). No todas las características se admiten en Windows PE.

- .NET Framework 4 también es compatible con la plataforma IA64.

- Para todas las plataformas, se recomienda actualizar al último Service Pack de Windows e instalar las actualizaciones críticas disponibles del [sitio web de Windows Update](http://go.microsoft.com/fwlink/?LinkId=168461) para garantizar la máxima compatibilidad y seguridad.

- En sistemas operativos de 64 bits, .NET Framework admite WOW64 (procesamiento de 32 bits en un equipo de 64 bits) y el procesamiento nativo de 64 bits.

## <a name="supported-server-operating-systems"></a>Sistemas operativos de servidor admitidos

| Sistema operativo | Ediciones compatibles | Preinstalado con el sistema operativo | Instalable por separado |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows Server 2016 | 64 bits | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] | .NET Framework 4.7 |
| [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] | 64 bits | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7 |
| [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] (edición de 64 bits) | 64 bits| [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7 |
| Windows Server 2008 R2 SP1|64 bits | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7 |
| Windows Server 2008 SP2|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] |

 **Notas:**

- [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] incluye [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], por lo que no tendrá que instalarlo por separado. Del mismo modo, [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] incluye [!INCLUDE[net_v451](../../../includes/net-v451-md.md)].

- .NET Framework se admite en el rol Server Core con Windows Server 2008 R2 SP1 o versiones posteriores, pero no se admite en Windows Server 2008 R2 for Itanium-Based Systems.

- En Windows Server 2008 SP2, .NET Framework no se admite en el rol Server Core.

- Para todas las plataformas, se recomienda instalar el último Service Pack de Windows y las actualizaciones críticas disponibles del [sitio web de Windows Update](http://go.microsoft.com/fwlink/?LinkId=168461) para garantizar la máxima compatibilidad y seguridad. La instalación del último Service Pack de Windows puede ser necesaria en algunos sistemas operativos.

- En sistemas operativos de 64 bits, .NET Framework admite WOW64 (procesamiento de 32 bits en un equipo de 64 bits) y el procesamiento nativo de 64 bits.

## <a name="see-also"></a>Vea también

[Guía de instalación](../../../docs/framework/install/index.md)   
[Introducción](../../../docs/framework/get-started/index.md)   
[Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)

