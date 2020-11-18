---
title: Seguridad basada en roles
ms.date: 07/15/2020
helpviewer_keywords:
- role-based security, about role-based security
- user authentication, principals
- principals [.NET]
- security [.NET], role-based
- permissions [.NET], principals
- authentication [.NET], principals
- role-based security, principals
ms.assetid: 578cc32b-5654-4d8b-9d8c-ebcbc5c75390
ms.openlocfilehash: a03cda3aac06cc247818ccea5c61c673225d7929
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824140"
---
# <a name="role-based-security"></a>Seguridad basada en roles

Suelen usarse roles en aplicaciones empresariales o financieras para aplicar la directiva. Por ejemplo, una aplicación puede imponer límites en el tamaño de la transacción que se va a procesar según si el usuario que realiza la solicitud es un miembro de rol especificado. Los empleados podrían tener autorización para procesar las transacciones que son inferiores a un umbral especificado, los supervisores podrían tener un límite mayor y los vicepresidentes podrían tener un límite aún mayor (o ningún límite). La seguridad basada en roles también se puede usar cuando una aplicación requiere varias aprobaciones para completar una acción. Este caso podría ser un sistema de compras en el que cualquier empleado puede generar una solicitud de compra, pero solo un agente de compras puede convertir la solicitud en un pedido de compras que se pueden enviar a un proveedor.  
  
 La seguridad basada en roles de .NET admite la autorización haciendo que la información sobre la entidad de seguridad, que se construye a partir de una identidad asociada, esté disponible para el subproceso actual. La identidad (y la entidad de seguridad que ayuda a definir) puede estar basada en una cuenta de Windows o puede ser una identidad personalizada no relacionada con una cuenta de Windows. Las aplicaciones .NET pueden tomar decisiones de autorización basadas en la identidad o la pertenencia a roles de la entidad de seguridad, o en ambas. Un rol es un conjunto de entidades de seguridad que tienen los mismos privilegios de seguridad (como un tesorero o un administrador). Una entidad de seguridad puede ser miembro de uno o varios roles. Por lo tanto, las aplicaciones pueden usar la pertenencia a un rol para determinar si una entidad de seguridad está autorizada para realizar una acción solicitada.  
  
 Para proporcionar facilidad de uso y coherencia con la seguridad de acceso del código, la seguridad basada en roles de .NET proporciona <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType> objetos que permiten a los Common Language Runtime realizar la autorización de forma similar a las comprobaciones de seguridad de acceso del código. La clase <xref:System.Security.Permissions.PrincipalPermission> representa la identidad o el rol con los que la entidad de seguridad debe coincidir y es compatible con las comprobaciones de seguridad declarativa e imperativa. También puede acceder directamente a la información de identidad de una entidad de seguridad y realizar las comprobaciones de identidad y de rol en el código cuando sea necesario.  
  
 .NET proporciona compatibilidad de seguridad basada en roles que es lo suficientemente flexible y extensible como para satisfacer las necesidades de una amplia gama de aplicaciones. Puede elegir interoperar con infraestructuras de autenticación existentes, como los servicios COM+ 1.0, o crear un sistema de autenticación personalizado. La seguridad basada en roles está especialmente indicada para aplicaciones web de ASP.NET, que se procesan principalmente en el servidor. Sin embargo, se puede usar la seguridad basada en roles de .NET en el cliente o el servidor.  
  
 Antes de leer esta sección, asegúrese de que comprende el material presentado en [conceptos clave de seguridad](key-security-concepts.md).  
  
## <a name="see-also"></a>Vea también
  
- [Objetos Principal e Identity](principal-and-identity-objects.md)
- [Conceptos clave de seguridad](key-security-concepts.md)
- <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType>
- [Seguridad de ASP.NET Core](/aspnet/core/security/)
