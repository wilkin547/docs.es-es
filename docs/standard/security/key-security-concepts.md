---
title: Conceptos clave de seguridad
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- unauthorized access
- permissions [.NET]
- security [.NET], about security
ms.assetid: 3cfced4f-ea02-4e66-ae98-d69286363e98
ms.openlocfilehash: a9f0703217b55c90c4e98503402d3fbf60a45ea7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831070"
---
# <a name="key-security-concepts"></a>Conceptos clave de seguridad

> [!NOTE]
> Este artículo se aplica a Windows.
>
> Para obtener información sobre ASP.NET Core, consulte [información general sobre la seguridad de ASP.net Core](/aspnet/core/security/).

.NET ofrece seguridad basada en roles para ayudar a solucionar los problemas de seguridad relacionados con el código móvil y ofrecer soporte técnico que permita a los componentes determinar qué usuarios están autorizados a realizar.  
  
## <a name="type-safety-and-security"></a>Protección y seguridad de tipos  

El código seguro de tipos sólo tiene acceso a las ubicaciones de memoria para las que tiene autorización. (En este debate, la seguridad de tipos se refiere específicamente a la seguridad de tipos de memoria y no debe confundirse con la seguridad de tipos en un respeto más amplio). Por ejemplo, el código seguro de tipos no puede leer valores de los campos privados de otro objeto. Sólo puede obtener acceso a tipos siguiendo métodos permitidos y perfectamente definidos.  
  
Durante la compilación Just-in-time (JIT), un proceso opcional de comprobación examina los metadatos y el lenguaje intermedio de Microsoft (MSIL) de los métodos a compilar a código máquina nativo, para comprobar si tienen seguridad de tipos. Este proceso se omite si el código tiene permiso para evitar la comprobación. Para información sobre la comprobación, consulte [Proceso de ejecución administrada](../managed-execution-process.md).  
  
Aunque la comprobación de la seguridad de tipos no es obligatoria para la ejecución de código administrado, la seguridad de tipos desempeña un rol crucial en el aislamiento del ensamblado y la exigencia de seguridad. Cuando el código tiene seguridad de tipos, Common Language Runtime puede aislar totalmente ensamblados entre sí. Este aislamiento ayuda a garantizar que los ensamblados no puedan ejercer influencias negativas entre sí y aumenta la confiabilidad de la aplicación. Los componentes seguros de tipos se pueden ejecutar de forma segura en el mismo proceso aunque dispongan de confianza en diferentes niveles. Cuando el código no tiene seguridad de tipos, pueden producirse efectos secundarios no deseados. Por ejemplo, el runtime no puede evitar la llamada de código administrado en código nativo (no administrado) ni la realización de operaciones malintencionadas. Cuando el código tiene seguridad de tipos, el mecanismo de exigencia de seguridad del motor en tiempo de ejecución garantiza que no tiene acceso a código nativo salvo que tenga permiso explícito para ello. El código sin seguridad de tipos debe haber obtenido permiso <xref:System.Security.Permissions.SecurityPermission> con el miembro de enumeración <xref:System.Security.Permissions.SecurityPermissionAttribute.SkipVerification%2A> transferido para la ejecución.  
  
Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../framework/misc/code-access-security-basics.md).  
  
## <a name="principal"></a>Principal  

Una entidad de seguridad (principal) representa la identidad y el rol de un usuario y actúa en nombre del usuario. La seguridad basada en roles en .NET admite tres tipos de entidades de seguridad:  
  
- Las entidades de seguridad genéricas representan usuarios y roles que son independientes de los roles y los usuarios de Windows.  
  
- Las entidades de seguridad de Windows representan a los usuarios de Windows y sus roles (o grupos de Windows). Una entidad de seguridad de Windows puede suplantar a otro usuario, lo que significa que la entidad de seguridad puede tener acceso a un recurso en nombre de un usuario presentando la identidad que pertenece a dicho usuario.  
  
- Una aplicación puede definir entidades de seguridad personalizadas que se adapten a las necesidades de esa aplicación en particular. Asimismo, se puede ampliar la noción básica de la identidad y los roles de la entidad de seguridad.  
  
Para más información, consulte [Objetos Principal e Identity](principal-and-identity-objects.md).  
  
## <a name="authentication"></a>Authentication  
La autenticación es el proceso de detectar y comprobar la identidad de una entidad de seguridad mediante el análisis de las credenciales del usuario y la validación de esas credenciales en alguna autoridad. Su código puede usar fácilmente la información obtenida durante la autenticación. También puede usar la seguridad basada en roles de .NET para autenticar al usuario actual y determinar si permite que esa entidad de seguridad tenga acceso a su código. Vea las sobrecargas del método <xref:System.Security.Principal.WindowsPrincipal.IsInRole%2A?displayProperty=nameWithType> para obtener ejemplos de cómo autenticar la entidad de seguridad para roles específicos. Por ejemplo, puede usar la sobrecarga <xref:System.Security.Principal.WindowsPrincipal.IsInRole%28System.String%29?displayProperty=nameWithType> para determinar si el usuario actual es miembro del grupo Administradores.  
  
Hoy en día se usan diversos mecanismos de autenticación, muchos de los cuales se pueden usar con la seguridad basada en roles de .NET. Algunos de los mecanismos más usados son básico, implícito, Passport, sistema operativo (como NTLM o Kerberos) o los mecanismos definidos por la aplicación.  
  
### <a name="example"></a>Ejemplo  

El ejemplo siguiente requiere que la entidad de seguridad activa sea un administrador. El parámetro `name` es `null`, que permite que cualquier usuario que sea administrador pase la petición.  
  
> [!NOTE]
> En Windows Vista, el control de cuentas de usuario (UAC) determina los privilegios de un usuario. Si es miembro del grupo Administradores integrados, se le asignarán dos símbolos (tokens) de acceso en tiempo de ejecución: un símbolo (token) de acceso de usuario estándar y un símbolo (token) de acceso de administrador. De forma predeterminada, se le asignará el rol de usuario estándar. Para ejecutar código que requiere permisos de administrador, primero debe elevar el nivel de sus privilegios de usuario estándar a administrador. Para ello, inicie una aplicación haciendo clic con el botón derecho en el icono de la aplicación e indique que desea ejecutarla como administrador.  
  
 [!code-cpp[Classic PrincipalPermission Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CPP/source.cpp#1)]
 [!code-csharp[Classic PrincipalPermission Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CS/source.cs#1)]
 [!code-vb[Classic PrincipalPermission Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/VB/source.vb#1)]  
  
 En el ejemplo siguiente se muestra cómo determinar la identidad de la entidad de seguridad y los roles disponibles para dicha entidad de seguridad. Una posible aplicación de este ejemplo sería la confirmación de que el usuario actual está en un rol permitido para usar la aplicación.  
  
 [!code-cpp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CPP/source.cpp#1)]
 [!code-csharp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CS/source.cs#1)]
 [!code-vb[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/VB/source.vb#1)]  
  
## <a name="authorization"></a>Authorization  

La autorización es el proceso de determinar si una entidad de seguridad puede realizar una acción solicitada. La autorización se produce después de la autenticación y usa información sobre la identidad y los roles de la entidad de seguridad para determinar a qué recursos puede tener acceso la entidad de seguridad. Puede usar la seguridad basada en roles de .NET para implementar la autorización.

## <a name="see-also"></a>Vea también

- [Seguridad de ASP.NET Core](/aspnet/core/security/)
