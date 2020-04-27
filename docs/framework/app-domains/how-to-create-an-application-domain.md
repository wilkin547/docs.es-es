---
title: Procedimiento para crear un dominio de aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: 83bf0ad96b352ed5c015723dd89aee7913d2a88e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119888"
---
# <a name="how-to-create-an-application-domain"></a>Procedimiento para crear un dominio de aplicación
Un host de Common Language Runtime habitual crea dominios de aplicación automáticamente cuando son necesarios, pero puede crear sus propios dominios de aplicación y cargar en ellos los ensamblados que desee administrar personalmente. También puede crear dominios de aplicación desde los que puede ejecutar el código.  
  
 Cree un dominio de aplicación mediante uno de los métodos **CreateDomain** sobrecargados en la clase <xref:System.AppDomain?displayProperty=nameWithType>. Puede asignar un nombre al dominio de aplicación y hacer referencia a él con ese nombre.  
  
 En el siguiente ejemplo se crea un dominio de aplicación, se le asigna el nombre `MyDomain` y, luego, se imprime el nombre del dominio host y el dominio de aplicación secundario recién creado en la consola.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Programar con dominios de aplicación](application-domains.md#programming-with-application-domains)
- [Utilizar dominios de aplicación](use.md)
