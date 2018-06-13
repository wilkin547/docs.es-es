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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94391471fecd92aeadec4da39cdd5b6f80bb6949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581169"
---
# <a name="replacing-a-principal-object"></a>Reemplazar un objeto Principal
Las aplicaciones que ofrecen servicios de autenticación deben poder reemplazar el objeto **Principal** (<xref:System.Security.Principal.IPrincipal>) de un subproceso determinado. Además, el sistema de seguridad debe ayudar a proteger la capacidad de reemplazar objetos **Principal** , porque un objeto **Principal** incorrecto asociado de forma malintencionada pone en peligro la seguridad de la aplicación mediante la notificación de una identidad o un rol falsos. Por lo tanto, las aplicaciones que requieren la capacidad de reemplazar **Principal** objetos deben concederse el <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> objeto para el control principal. (Tenga en cuenta que este permiso no se requiere para realizar comprobaciones de seguridad basada en roles o para crear objetos **Principal** ).  
  
 El objeto **Principal** actual se puede reemplazar realizando las tareas siguientes:  
  
1.  Cree el objeto **Principal** de reemplazo y el objeto **Identity** asociado.  
  
2.  Adjunte el nuevo objeto **Principal** al contexto de llamada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo se crea un objeto de entidad de seguridad genérico y cómo usarlo para establecer la entidad de seguridad de un subproceso.  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
 [Objetos Principal e Identity](../../../docs/standard/security/principal-and-identity-objects.md)
