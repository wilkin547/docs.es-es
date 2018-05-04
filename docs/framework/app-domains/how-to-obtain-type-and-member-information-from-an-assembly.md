---
title: 'Cómo: Obtener información sobre tipos y miembros desde un ensamblado'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 390afb392c06d5ce003d69f028cd667deb4d86c8
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a>Cómo: Obtener información sobre tipos y miembros desde un ensamblado
El espacio de nombres <xref:System.Reflection> contiene muchos métodos para obtener información de un ensamblado. En esta sección se muestra uno de estos métodos. Para obtener información adicional, vea [Reflection Overview](../../../docs/framework/reflection-and-codedom/reflection.md) (Información general de la reflexión).  
  
 En el ejemplo siguiente se obtiene información sobre tipos y miembros desde un ensamblado.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a>Vea también  
 [Programar con dominios de aplicación](./application-domains.md#programming-with-application-domains) [Reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)
