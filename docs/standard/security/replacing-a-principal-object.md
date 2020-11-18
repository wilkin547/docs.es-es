---
title: Reemplazar un objeto Principal
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET], replacing principal objects
- security [.NET], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: b8f7a8fbd3b9c65126d6a3a65a5f6722f2ad93de
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824179"
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [Objetos Principal e Identity](principal-and-identity-objects.md)
- [Seguridad de ASP.NET Core](/aspnet/core/security/)
