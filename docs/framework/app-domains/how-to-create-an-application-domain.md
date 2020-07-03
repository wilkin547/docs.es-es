---
title: Procedimiento para crear un dominio de aplicación
description: Revise cómo crear un dominio de aplicación en .NET. Un dominio de aplicación puede crearse para ejecutar código o para cargar ensamblados con el fin de administrarlos personalmente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: 8e44e682f64854dbc0181b26f6ed3fa2905b7814
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104811"
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
