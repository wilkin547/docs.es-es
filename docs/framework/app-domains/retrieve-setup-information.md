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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80c9fe6de0fca86497ffe84cd8dadf0eb8cef6c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108958"
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
- [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)
