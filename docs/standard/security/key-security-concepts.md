---
title: "Key Security Concepts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "unauthorized access"
  - "permissions [.NET Framework]"
  - "security [.NET Framework], about security"
ms.assetid: 3cfced4f-ea02-4e66-ae98-d69286363e98
caps.latest.revision: 22
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 20
---
# Key Security Concepts
Microsoft .NET Framework ofrece transparencia en seguridad, seguridad de acceso del código y seguridad basada en roles para ayudar a solucionar problemas de seguridad relativos a código móvil y para permitir que los componentes determinen qué usuarios tienen autorización para operar.  Estos mecanismos de seguridad usan un modelo sencillo y coherente para que los desarrolladores familiarizados con la seguridad de acceso del código puedan utilizar fácilmente la seguridad basada en roles y viceversa.  Tanto la seguridad de acceso del código como la seguridad basada en roles se implementan mediante una infraestructura común proporcionada por Common Language Runtime.  
  
> [!NOTE]
>  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la transparencia en seguridad es el mecanismo predeterminado de seguridad.  La transparencia en seguridad separa el código que se ejecuta como parte de la aplicación del código que se ejecuta como parte de la infraestructura.  Para obtener más información, consulte el artículo sobre [Security\-Transparent Code](../../../docs/framework/misc/security-transparent-code.md).  
  
 Puesto que usan el mismo modelo e infraestructura, la seguridad de acceso del código y la seguridad basada en roles comparten varios conceptos subyacentes, que se describen en esta sección.  Asegúrese de que está familiarizado con estos conceptos antes de leer la documentación de seguridad de acceso del código de .NET Framework y la seguridad basada en roles.  
  
## Permisos de seguridad  
 Common Language Runtime permite que el código realice únicamente las operaciones para las que tiene permiso.  El runtime usa objetos denominados permisos para aplicar restricciones en el código administrado.  El runtime proporciona clases de permiso integradas en varios espacios de nombres y también admite el diseño y la implementación de clases de permiso personalizadas.  
  
 Hay dos tipos de permisos y cada una tiene una finalidad específica:  
  
-   Los permisos de acceso del código representan el acceso a un recurso protegido o la capacidad de realizar una operación protegida.  
  
-   Los permisos de seguridad basada en roles proporcionan un mecanismo para descubrir si un usuario \(o el agente que actúa en su nombre\) tiene una identidad concreta o es miembro de una función especificada.  <xref:System.Security.Permissions.PrincipalPermission> es el único permiso de seguridad basada en roles.  
  
 Los permisos de seguridad pueden ser en forma de una clase de permiso \(seguridad imperativa\) o de un atributo que representa una clase de permiso \(seguridad declarativa\).  La clase base para permisos de seguridad es <xref:System.Security.CodeAccessPermission?displayProperty=fullName>; la clase base para los atributos de permiso de seguridad es <xref:System.Security.Permissions.CodeAccessSecurityAttribute?displayProperty=fullName>.  
  
 A una aplicación, en forma de un ensamblado, se le concede un conjunto de permisos en el momento en que se carga en un dominio de aplicación.  Normalmente, las concesiones se realizan mediante el uso de conjuntos de permisos predefinidos que vienen determinados por el método <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=fullName>.  El conjunto de permisos determina los permisos que el código tiene a su disposición.  El runtime concede permisos basados en la ubicación de origen del código \(por ejemplo, la máquina local, intranet local o Internet\).  El código también puede obtener permisos especiales si se carga en un espacio aislado.  Para obtener más información, vea el artículo sobre la [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
 Los usos principales de permisos son los siguientes:  
  
-   El código de biblioteca puede exigir que sus llamadores tengan permisos específicos.  Si coloca un <xref:System.Security.CodeAccessPermission.Demand%2A> para un permiso en el código, se espera que todo el código que usa su código tenga ese permiso para poder ejecutarse.  Las peticiones \(demands\) pueden usarse para determinar si los llamadores tienen acceso a recursos específicos o para detectar la identidad del llamador.  
  
-   El código puede usar permisos para denegar el acceso a los recursos que desea proteger.  Puede usar <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> para especificar un conjunto de permisos limitados y denegar implícitamente el resto de los permisos.  Sin embargo, no le recomendamos usar <xref:System.Security.Permissions.SecurityAction> para prohibir el acceso con el fin de proteger contra el uso indebido intencionado.  Los ensamblados llamados, que tienen los permisos denegados implícitamente en su conjunto de permisos, pueden invalidar los permisos denegados mediante un <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> para cualquier permiso que deseen usar.  Por ejemplo, si permite solo <xref:System.Security.Permissions.UIPermission> y llama a un ensamblado que tiene inherentemente <xref:System.Security.Permissions.FileIOPermission>, el ensamblado puede hacer simplemente un <xref:System.Security.Permissions.SecurityAction> para <xref:System.Security.Permissions.FileIOPermission> y realizar operaciones de archivo.  Es la única manera de proteger los recursos de forma segura de código no seguro en los ensamblados con referencia es ejecutar ese código con un conjunto de permisos que no incluya esos permisos.  
  
### Permisos de acceso del código  
 Los permisos de acceso del código son objetos de permiso que se usan para ayudar a proteger los recursos y las operaciones contra el uso no autorizado.  Son una parte fundamental del mecanismo de Common Language Runtime para aplicar restricciones de seguridad en el código administrado.  
  
 Cada permiso de acceso del código representa uno de los siguientes derechos:  
  
-   El derecho a tener acceso a un recurso protegido, como archivos o variables de entorno.  
  
-   El derecho a realizar una operación protegida, como tener acceso a código no administrado.  
  
 Todos los permisos de acceso del código pueden solicitarse o exigirse mediante código, y el runtime decide qué permisos, si los hay, se deben conceder al código.  
  
 Cada permiso de acceso del código se deriva de la clase <xref:System.Security.CodeAccessPermission>, lo que significa que todos los permisos de acceso del código tienen métodos en común, como **Demand**, **Assert**, **Deny**, **PermitOnly**, **IsSubsetOf**, **Intersect** y **Union**.  
  
> [!IMPORTANT]
>  En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], se ha quitado la compatibilidad de runtime para exigir las solicitudes de permiso <xref:System.Security.Permissions.SecurityAction>, <xref:System.Security.Permissions.SecurityAction>, <xref:System.Security.Permissions.SecurityAction> y <xref:System.Security.Permissions.SecurityAction>.  Estas solicitudes no deben usarse en código basado en [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] o en una versión posterior.  Para obtener más información sobre este y otros cambios, vea el artículo sobre [Cambios de seguridad](../../../docs/framework/security/security-changes.md).  
  
### Permisos de seguridad basada en roles  
 <xref:System.Security.Permissions.PrincipalPermission> es un permiso de seguridad basada en roles que puede usarse para determinar si un usuario tiene una identidad especificada o es miembro de un rol especificado.  **PrincipalPermission** es el único permiso de seguridad basada en roles proporcionado por la biblioteca de clases de .NET Framework.  
  
## Protección y seguridad de tipos  
 El código seguro de tipos sólo tiene acceso a las ubicaciones de memoria para las que tiene autorización.  A efectos de esta descripción, la seguridad de tipos se refiere concretamente a la seguridad de tipos en memoria y no debe confundirse con la seguridad de tipos en un sentido más amplio. Por ejemplo, el código seguro de tipos no puede leer valores de los campos privados de otro objeto.  Sólo puede obtener acceso a tipos siguiendo métodos permitidos y perfectamente definidos.  
  
 Durante la compilación Just\-in\-time \(JIT\), un proceso opcional de comprobación examina los metadatos y el lenguaje intermedio de Microsoft \(MSIL\) de los métodos a compilar a código máquina nativo, para comprobar si tienen seguridad de tipos.  Este proceso se omite si el código tiene permiso para evitar la comprobación.  Para obtener más información acerca de la comprobación, vea el artículo sobre el [Proceso de ejecución administrada](../../../docs/standard/managed-execution-process.md).  
  
 Aunque la comprobación de la seguridad de tipos no es obligatoria para la ejecución de código administrado, la seguridad de tipos desempeña un rol crucial en el aislamiento del ensamblado y la exigencia de seguridad.  Cuando el código tiene seguridad de tipos, Common Language Runtime puede aislar totalmente ensamblados entre sí.  Este aislamiento ayuda a garantizar que los ensamblados no puedan ejercer influencias negativas entre sí y aumenta la confiabilidad de la aplicación.  Los componentes seguros de tipos se pueden ejecutar de forma segura en el mismo proceso aunque dispongan de confianza en diferentes niveles.  Cuando el código no tiene seguridad de tipos, pueden producirse efectos secundarios no deseados.  Por ejemplo, el runtime no puede evitar la llamada de código administrado en código nativo \(no administrado\) ni la realización de operaciones malintencionadas.  Cuando el código tiene seguridad de tipos, el mecanismo de exigencia de seguridad del motor en tiempo de ejecución garantiza que no tiene acceso a código nativo salvo que tenga permiso explícito para ello.  El código sin seguridad de tipos debe haber obtenido permiso <xref:System.Security.Permissions.SecurityPermission> con el miembro de enumeración <xref:System.Security.Permissions.SecurityPermissionAttribute.SkipVerification%2A> transferido para la ejecución.  
  
 Para obtener más información, consulte el artículo sobre cómo [NIB: Writing Verifiably Type\-Safe Code](http://msdn.microsoft.com/es-es/d18f10ef-3b48-4f47-8726-96714021547b).  
  
## Principal  
 Una entidad de seguridad \(principal\) representa la identidad y el rol de un usuario y actúa en nombre del usuario.  La seguridad basada en roles de .NET Framework admite tres tipos de entidades de seguridad:  
  
-   Las entidades de seguridad genéricas representan usuarios y roles que son independientes de los roles y los usuarios de Windows.  
  
-   Las entidades de seguridad de Windows representan a los usuarios de Windows y sus roles \(o grupos de Windows\).  Una entidad de seguridad de Windows puede suplantar a otro usuario, lo que significa que la entidad de seguridad puede tener acceso a un recurso en nombre de un usuario presentando la identidad que pertenece a dicho usuario.  
  
-   Una aplicación puede definir entidades de seguridad personalizadas que se adapten a las necesidades de esa aplicación en particular.  Asimismo, se puede ampliar la noción básica de la identidad y los roles de la entidad de seguridad.  
  
 Para obtener más información, consulte el artículos sobre los [Principal and Identity Objects](../../../docs/standard/security/principal-and-identity-objects.md).  
  
## Autenticación  
 La autenticación es el proceso de detectar y comprobar la identidad de una entidad de seguridad mediante el análisis de las credenciales del usuario y la validación de esas credenciales en alguna autoridad.  Su código puede usar fácilmente la información obtenida durante la autenticación.  También puede usar la seguridad basada en roles de .NET Framework para autenticar al usuario actual y para determinar si esa entidad de seguridad puede tener acceso a su código.  Vea las sobrecargas del método <xref:System.Security.Principal.WindowsPrincipal.IsInRole%2A?displayProperty=fullName> para obtener ejemplos de cómo autenticar la entidad de seguridad para roles específicos.  Por ejemplo, puede usar la sobrecarga <xref:System.Security.Principal.WindowsPrincipal.IsInRole%28System.String%29?displayProperty=fullName> para determinar si el usuario actual es miembro del grupo Administradores.  
  
 Hoy en día se usan diversos mecanismos de autenticación, muchos de los cuales pueden utilizarse con la seguridad basada en roles de .NET Framework.  Algunos de los mecanismos más usados son básico, implícito, Passport, sistema operativo \(como NTLM o Kerberos\) o los mecanismos definidos por la aplicación.  
  
### Ejemplo  
 El ejemplo siguiente requiere que la entidad de seguridad activa sea un administrador.  El parámetro `name` es `null`, que permite que cualquier usuario que sea administrador pase la petición.  
  
> [!NOTE]
>  En Windows Vista, el control de cuentas de usuario \(UAC\) determina los privilegios de un usuario.  Si es miembro del grupo Administradores integrados, se le asignarán dos símbolos \(tokens\) de acceso en tiempo de ejecución: un símbolo \(token\) de acceso de usuario estándar y un símbolo \(token\) de acceso de administrador.  De forma predeterminada, se le asignará el rol de usuario estándar.  Para ejecutar código que requiere permisos de administrador, primero debe elevar el nivel de sus privilegios de usuario estándar a administrador.  Para ello, inicie una aplicación haciendo clic con el botón derecho en el icono de la aplicación e indique que desea ejecutarla como administrador.  
  
 [!code-cpp[Classic PrincipalPermission Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CPP/source.cpp#1)]
 [!code-csharp[Classic PrincipalPermission Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CS/source.cs#1)]
 [!code-vb[Classic PrincipalPermission Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/VB/source.vb#1)]  
  
 En el ejemplo siguiente se muestra cómo determinar la identidad de la entidad de seguridad y los roles disponibles para dicha entidad de seguridad.  Una posible aplicación de este ejemplo sería la confirmación de que el usuario actual está en un rol permitido para usar la aplicación.  
  
 [!code-cpp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CPP/source.cpp#1)]
 [!code-csharp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CS/source.cs#1)]
 [!code-vb[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/VB/source.vb#1)]  
  
## Autorización  
 La autorización es el proceso de determinar si una entidad de seguridad puede realizar una acción solicitada.  La autorización se produce después de la autenticación y usa información sobre la identidad y los roles de la entidad de seguridad para determinar a qué recursos puede tener acceso la entidad de seguridad.  Para implementar la autorización, se puede usar la seguridad basada en roles de .NET Framework.  
  
## Problemas de seguridad de las palabras clave virtuales internas  
 Nunca base la seguridad de su aplicación en un miembro que esté marcado con el modificador [internal](../Topic/internal%20\(C%23%20Reference\).md) [virtual](../Topic/virtual%20\(C%23%20Reference\).md) en C\# \([Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) [Overridable](../Topic/Overridable%20\(Visual%20Basic\).md) [Friend](../Topic/Friend%20\(Visual%20Basic\).md) en Visual Basic\).  A pesar de que los miembros marcados con estos modificadores solo pueden ser invalidados por otros miembros del ensamblado actual, únicamente aplican esta regla los lenguajes C\# y Visual Basic.  El runtime no la aplica.  Por lo tanto, es posible invalidar los miembros marcados como **internal virtual** en C\# y **Overloads Overridable Friend** en Visual Basic usando el Lenguaje Intermedio de Microsoft o cualquier otro lenguaje que no aplique esta regla.  
  
## Vea también  
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)