---
title: "Ejecución de aplicaciones de .NET Framework 1.1 en Windows 8, Windows 8.1 o Windows 10"
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
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4ae88205af37d8ffb49e845942e83432357d4bdd
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Ejecución de aplicaciones de .NET Framework 1.1 en Windows 8, Windows 8.1 o Windows 10

.NET Framework 1.1 no se admite en los sistemas operativos [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] ni en Windows 10. En algunos casos, se identifica específicamente que .NET Framework 1.1 es necesario para que una aplicación se ejecute. En esos casos, debe ponerse en contacto con el fabricante independiente de software (ISV) para conseguir que la aplicación actualizada se ejecute en [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] o una versión posterior. Para más información, vea [Migrar de .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>Instalación de .NET Framework 1.1 desde un CD o desde el Centro de descarga

No es posible instalar manualmente .NET Framework 1.1 en [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] ni en Windows 10. Ya no se admite. Si intenta instalar el paquete, aparece el mensaje de error siguiente: “El programa de instalación no puede continuar porque esta versión de .NET Framework no es compatible con una instalada previamente”. Para solucionar este problema, instale [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22). Esta versión incluye .NET Framework 2.0 (la versión siguiente a .NET Framework 1.1), que es compatible en [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] y en Windows 10. Siempre debería intentar instalar primero la aplicación para determinar si se va a actualizar automáticamente a una versión posterior de .NET Framework. De no ser así, póngase en contacto con el ISV para obtener una actualización de la aplicación.

## <a name="see-also"></a>Vea también

[Migrar de .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)

