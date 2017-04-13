---
title: "Secure Coding Guidelines | Microsoft Docs"
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
  - "managed wrapper to native code implementation"
  - "secure coding"
  - "reusable components"
  - "library code that exposes protected resources"
  - "code, security"
  - "code security"
  - "secure coding, options"
  - "components [.NET Framework], security"
  - "code security, options"
  - "security-neutral code"
  - "security [.NET Framework], coding guidelines"
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Secure Coding Guidelines
La seguridad basada en pruebas y la seguridad de acceso por código ofrecen mecanismos explícitos y muy eficaces para implementar la seguridad. La mayoría del código de aplicación puede usar simplemente la infraestructura implementada por .NET Framework. En algunos casos, se requiere la seguridad específica de aplicación adicional, creada ampliando el sistema de seguridad o mediante nuevos métodos ad hoc.  
  
 Con los permisos aplicados por .NET Framework y otra aplicación de su código, debe establecer barreras para evitar que código malintencionado obtenga información que no quiera que tenga o que realice otras acciones no deseadas. Además, debe lograr un equilibrio entre la seguridad y la facilidad de uso en todos los escenarios esperados mediante código de confianza.  
  
 Esta información general describe las diferentes formas en que se puede diseñar código para que funcione con el sistema de seguridad.  
  
> [!NOTE]
>  En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] se introdujeron cambios importantes tanto en el modelo de seguridad de .NET Framework como en la terminología. Para más información sobre estos cambios, vea [Cambios de seguridad](../../../docs/framework/security/security-changes.md).  
  
## Seguridad de acceso del código y código de confianza parcial  
 .NET Framework proporciona seguridad de acceso del código \(CAS\), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.  Puesto que la seguridad de acceso del código en .NET Framework no garantiza el aislamiento del código, no debe usarse como límite de seguridad para código de confianza parcial, especialmente si se trata de código de origen desconocido. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.  
  
 Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.  
  
## Código neutral respecto a la seguridad  
 El código neutral respecto a la seguridad no hace nada explícito con el sistema de seguridad. Se ejecuta con los permisos que recibe. Aunque las aplicaciones que no pudieron detectar las excepciones de seguridad asociadas a operaciones protegidas \(como el uso de archivos, las redes etc.\) pueden generar una excepción no controlada, el código neutral respecto a la seguridad todavía aprovecha las tecnologías de seguridad de .NET Framework.  
  
 Una biblioteca neutral respecto a la seguridad tiene características especiales que debe conocer. Supongamos que la biblioteca ofrece elementos de la API que usan archivos o llaman a código no administrado; si el código no tiene el permiso correspondiente, no se ejecutará como se describe. Sin embargo, incluso si el código tiene el permiso, cualquier código de aplicación que le llame debe tener el mismo permiso para poder funcionar. Si el código de llamada no dispone del permiso adecuado, aparecerá una <xref:System.Security.SecurityException> como resultado del recorrido de la pila de seguridad de acceso al código.  
  
## Código de aplicación que no es un componente reutilizable  
 Si el código forma parte de una aplicación a la que no llamará otro código, la seguridad es sencilla y es posible que la codificación especial no sea necesaria. Sin embargo, recuerde que el código malintencionado puede llamar a su código. Aunque la seguridad de acceso a código puede evitar que código malintencionado obtenga acceso a recursos, dicho código todavía podría leer valores de sus campos o propiedades que puedan contener información confidencial.  
  
 Además, si el código acepta la entrada del usuario desde Internet o de otras fuentes no confiables, debe tener cuidado con la entrada malintencionada.  
  
## Implementación de contenedor administrado en código nativo  
 Normalmente en este escenario se implementa alguna funcionalidad de utilidad en código nativo que quiere que esté disponible para código administrado. Los contenedores administrados son sencillos de escribir mediante la invocación de plataforma o interoperabilidad COM. Sin embargo, si lo hace, los llamadores de los contenedores deben tener derechos de código no administrado para ser correctos. Con la directiva predeterminada, esto significa que el código descargado de una intranet o de Internet no funcionará con los contenedores.  
  
 En lugar de darle a todas las aplicaciones que usan estos contenedores derechos de código no administrado , es mejor dar estos derechos únicamente al código del contenedor. Si la funcionalidad subyacente no expone ningún recurso y la implementación es igual de segura, el contenedor solo necesita imponer sus derechos, lo que permite a cualquier código llamar a través de él. Cuando se trate de recursos, la codificación de seguridad debe ser la mismo que el caso de código de biblioteca descrito en la siguiente sección. Dado que el contenedor puede exponer a los llamadores a esos recursos, se necesita una cuidadosa comprobación de la seguridad del código nativo, lo que es responsabilidad del contenedor.  
  
## Código de biblioteca que expone recursos protegidos  
 Este es el enfoque más eficaz y, por tanto, potencialmente peligroso \(si se realiza incorrectamente\) para la codificación de seguridad: la biblioteca actúa como una interfaz para que otro código obtenga acceso a determinados recursos que no están disponibles de otra manera, de la misma forma que las clases de .NET Framework aplican permisos para los recursos que usan. Siempre que exponga un recurso, su código debe requerir primero el permiso adecuado para el recurso \(es decir, debe realizar una comprobación de seguridad\) y luego declarar sus derechos para llevar a cabo la operación real.  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)|Se explica cómo ejecutar una aplicación de confianza parcial en un entorno de seguridad restringido, que limita los permisos de acceso al código que se le han concedido.|  
|[Securing State Data](../../../docs/standard/security/securing-state-data.md)|Se describe cómo proteger los miembros privados.|  
|[Securing Method Access](../../../docs/framework/misc/securing-method-access.md)|Se describe cómo ayudar a proteger los métodos para que no les llame código de confianza parcial.|  
|[Securing Wrapper Code](../../../docs/framework/misc/securing-wrapper-code.md)|Se describen cuestiones de seguridad para el código que ajusta otro código.|  
|[Security and Public Read\-only Array Fields](../../../docs/framework/misc/security-and-public-read-only-array-fields.md)|Se describen cuestiones de seguridad del código que usa las matrices públicas de solo lectura que se encuentran en las bibliotecas de .NET Framework.|  
|[Securing Exception Handling](../../../docs/framework/misc/securing-exception-handling.md)|Se describen cuestiones de seguridad para controlar excepciones.|  
|[Security and User Input](../../../docs/standard/security/security-and-user-input.md)|Se describen cuestiones de seguridad para las aplicaciones que aceptan la entrada del usuario.|  
|[Security and Remoting Considerations](../../../docs/framework/misc/security-and-remoting-considerations.md)|Se describen cuestiones de seguridad  para las aplicaciones que se comunican entre dominios de aplicación.|  
|[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)|Se describen cuestiones de seguridad al serializar objetos.|  
|[Security and Race Conditions](../../../docs/standard/security/security-and-race-conditions.md)|Se describe cómo evitar condiciones de anticipación en el código.|  
|[Security and On\-the\-Fly Code Generation](../../../docs/standard/security/security-and-on-the-fly-code-generation.md)|Se describen cuestiones de seguridad para las aplicaciones que generan código dinámico.|  
|[Security and Setup Issues](../Topic/Security%20and%20Setup%20Issues.md)|Se describen consideraciones para las pruebas y la configuración de la aplicación.|  
|[Code Access Security](../../../docs/framework/misc/code-access-security.md)|Se describe detalladamente la seguridad de acceso a código de .NET Framework y se ofrecen instrucciones para usarla en el código.|  
|[Role\-Based Security](../../../docs/standard/security/role-based-security.md)|Se describe detalladamente la seguridad basada en roles de .NET Framework y se ofrecen instrucciones para usarla en el código.|