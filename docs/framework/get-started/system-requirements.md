---
title: Requisitos de sistema de .NET Framework
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- software requirements
- .NET Framework, system requirements
- system requirements
- operating systems supported
- hardware requirements
ms.assetid: 298275e2-da1d-4618-9f74-6a3567832350
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b08bd7b78a8606f61c266da51f4079f0b5f4aac6
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2017
---
# <a name="net-framework-system-requirements"></a>Requisitos de sistema de .NET Framework

Las tablas de este tema indican los requisitos de hardware, sistema operativo y software para .NET Framework 4.5 y sus versiones secundarias (4.5.1 y 4.5.2), el [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y sus versiones secundarias (4.6.1 y 4.6.2) y la 4.7 de .NET Framework y su punto versión (4.7.1). Los entornos de desarrollo que permiten desarrollar aplicaciones para .NET Framework tienen otros requisitos diferentes.

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
| Actualización de los creadores de otoño de Windows 10 | 32 bits y 64 bits | .NET framework 4.7.1 | |
| Windows 10 Creators Update | 32 bits y 64 bits | .NET Framework 4.7 | .NET framework 4.7.1 | 
| Actualización de aniversario de Windows 10 | 32 bits y 64 bits | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| Actualización de noviembre de Windows 10 | 32 bits y 64 bits | [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] | |
| Windows 10  | 32 bits y 64 bits | [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] | [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] |
| [!INCLUDE[win81](../../../includes/win81-md.md)] | 32 bits, 64 bits y ARM | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| [!INCLUDE[win8](../../../includes/win8-md.md)] | 32 bits, 64 bits y ARM | [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] |
| Windows 7 SP1|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1|
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
| Windows Server, versión 1709 | 64 bits | .NET framework 4.7.1 | -- |
| Windows Server 2016 | 64 bits | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] | .NET Framework 4.7<br/><br/> .NET framework 4.7.1 |
| Windows Server 2012 R2 | 64 bits | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/> .NET framework 4.7.1 |
| Windows Server 2012 (versión de 64 bits) | 64 bits| [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| Windows Server 2008 R2 SP1|64 bits | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| Windows Server 2008 SP2|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] |

 **Notas:**

- [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] incluye [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], por lo que no tendrá que instalarlo por separado. Del mismo modo, [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] incluye [!INCLUDE[net_v451](../../../includes/net-v451-md.md)].

- .NET Framework proporciona compatibilidad limitada para el rol Server Core con Windows Server 2008 R2 SP1 o posterior. Vea [la funcionalidad de .NET de Server Core](https://msdn.microsoft.com/library/ee391632.aspx) para obtener una lista de API no compatibles.

- .NET Framework no se admite en Windows Server 2008 R2 para Itanium.

- En Windows Server 2008 SP2, .NET Framework no se admite en el rol Server Core.

- Para todas las plataformas, se recomienda instalar el último Service Pack de Windows y las actualizaciones críticas disponibles del [sitio web de Windows Update](http://go.microsoft.com/fwlink/?LinkId=168461) para garantizar la máxima compatibilidad y seguridad. La instalación del último Service Pack de Windows puede ser necesaria en algunos sistemas operativos.

- En sistemas operativos de 64 bits, .NET Framework admite WOW64 (procesamiento de 32 bits en un equipo de 64 bits) y el procesamiento nativo de 64 bits.

## <a name="see-also"></a>Vea también

[Guía de instalación](../../../docs/framework/install/index.md)   
[Introducción](../../../docs/framework/get-started/index.md)   
[Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)
