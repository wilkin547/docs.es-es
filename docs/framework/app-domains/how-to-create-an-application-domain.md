---
title: "Cómo: Crear un dominio de aplicación | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 928a5d897e7df288f07ec32aff43f28617ef9623
ms.contentlocale: es-es
ms.lasthandoff: 06/02/2017

---
# <a name="how-to-create-an-application-domain"></a>Cómo: Crear un dominio de aplicación
Un host de Common Language Runtime habitual crea dominios de aplicación automáticamente cuando son necesarios, pero puede crear sus propios dominios de aplicación y cargar en ellos los ensamblados que desee administrar personalmente. También puede crear dominios de aplicación desde los que puede ejecutar el código.  
  
 Cree un dominio de aplicación mediante uno de los métodos **CreateDomain** sobrecargados en la clase <xref:System.AppDomain?displayProperty=fullName>. Puede asignar un nombre al dominio de aplicación y hacer referencia a él con ese nombre.  
  
 En el siguiente ejemplo se crea un dominio de aplicación, se le asigna el nombre `MyDomain` y, luego, se imprime el nombre del dominio host y el dominio de aplicación secundario recién creado en la consola.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)] [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)] [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Programar con dominios de aplicación](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)
