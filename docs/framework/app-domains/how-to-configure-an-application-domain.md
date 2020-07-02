---
title: Procedimiento para configurar un dominio de aplicación
description: Configure un dominio de aplicación en .NET. Puede proporcionar información de configuración a CLR para un nuevo dominio de aplicación mediante la clase AppDomainSetup.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: 27afcf161bec74143fafb5dceb20597de73e23d4
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104858"
---
# <a name="how-to-configure-an-application-domain"></a>Procedimiento para configurar un dominio de aplicación
Puede proporcionar información de configuración a Common Language Runtime para un nuevo dominio de aplicación mediante la clase <xref:System.AppDomainSetup>. Al crear sus propios dominios de aplicación, la propiedad más importante es <xref:System.AppDomainSetup.ApplicationBase%2A>. Las otras propiedades **AppDomainSetup** las usan principalmente los hosts en tiempo de ejecución para configurar un dominio de aplicación determinado.  
  
 La propiedad **ApplicationBase** define el directorio raíz de la aplicación. Cuando el tiempo de ejecución tiene que satisfacer una solicitud de tipo, busca el ensamblado que contiene el tipo en el directorio especificado por la propiedad **ApplicationBase**.  
  
> [!NOTE]
> Un nuevo dominio de aplicación solo hereda la propiedad **ApplicationBase** del creador.  
  
 En el ejemplo siguiente se crea una instancia de la clase **AppDomainSetup**, se usa esta clase para crear un dominio de aplicación, se escribe la información en la consola y, luego, se descarga el dominio de aplicación.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Programar con dominios de aplicación](application-domains.md#programming-with-application-domains)
- [Utilizar dominios de aplicación](use.md)
