---
title: Reemplazar un objeto Principal
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: 056bd0bbafe0e7dc84d8d0c532ff844370c59230
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291219"
---
# <a name="replacing-a-principal-object"></a>Reemplazar un objeto Principal
Las aplicaciones que ofrecen servicios de autenticación deben poder reemplazar el objeto **Principal** (<xref:System.Security.Principal.IPrincipal>) de un subproceso determinado. Además, el sistema de seguridad debe ayudar a proteger la capacidad de reemplazar objetos **Principal** , porque un objeto **Principal** incorrecto asociado de forma malintencionada pone en peligro la seguridad de la aplicación mediante la notificación de una identidad o un rol falsos. Por lo tanto, las aplicaciones que requieren la capacidad de reemplazar objetos **Principal** necesitan que se les conceda el objeto <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> para el control de la entidad de seguridad. (Tenga en cuenta que este permiso no se requiere para realizar comprobaciones de seguridad basada en roles o para crear objetos **Principal** ).  
  
 El objeto **Principal** actual se puede reemplazar realizando las tareas siguientes:  
  
1. Cree el objeto **Principal** de reemplazo y el objeto **Identity** asociado.  
  
2. Adjunte el nuevo objeto **Principal** al contexto de llamada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo se crea un objeto de entidad de seguridad genérico y cómo usarlo para establecer la entidad de seguridad de un subproceso.  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [Objetos Principal e Identity](principal-and-identity-objects.md)
