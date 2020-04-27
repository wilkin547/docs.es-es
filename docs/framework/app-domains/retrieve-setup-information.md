---
title: Recuperar información de instalación de un dominio de aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
ms.openlocfilehash: 4d06a8a3ccfa35af283323478ee44a7da63d896d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119743"
---
# <a name="retrieving-setup-information-from-an-application-domain"></a>Recuperar información de instalación de un dominio de aplicación
Cada instancia de un dominio de aplicación consta de propiedades e información <xref:System.AppDomainSetup>. Puede recuperar información de instalación de un dominio de aplicación mediante la clase <xref:System.AppDomain?displayProperty=nameWithType>. Esta clase proporciona varios miembros que recuperan información de configuración sobre un dominio de aplicación.  
  
 También puede consultar el objeto **AppDomainSetup** del dominio de aplicación para la obtener la información de configuración pasada al dominio al crearse.  
  
 En el ejemplo siguiente se crea un dominio de aplicación y, después, se imprimen varios valores de miembro en la consola.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 En el ejemplo siguiente se establece y, después, se recupera la información de configuración de un dominio de aplicación. Observe que `AppDomain.SetupInformation.ApplicationBase` obtiene la información de configuración.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Programar con dominios de aplicación](application-domains.md#programming-with-application-domains)
- [Utilizar dominios de aplicación](use.md)
