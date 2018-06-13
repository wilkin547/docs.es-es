---
title: Instrucciones de codificación segura
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET Framework], security
- code security, options
- security-neutral code
- security [.NET Framework], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8d61e76a657c7341ec7dfcede6d7dc9943d4659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588166"
---
# <a name="secure-coding-guidelines"></a>Instrucciones de codificación segura
La seguridad basada en pruebas y la seguridad de acceso por código ofrecen mecanismos explícitos y muy eficaces para implementar la seguridad. La mayoría del código de aplicación puede usar simplemente la infraestructura implementada por .NET Framework. En algunos casos, se requiere la seguridad específica de aplicación adicional, creada ampliando el sistema de seguridad o mediante nuevos métodos ad hoc.  
  
 Con los permisos aplicados por .NET Framework y otra aplicación de su código, debe establecer barreras para evitar que código malintencionado obtenga información que no quiera que tenga o que realice otras acciones no deseadas. Además, debe lograr un equilibrio entre la seguridad y la facilidad de uso en todos los escenarios esperados mediante código de confianza.  
  
 Esta información general describe las diferentes formas en que se puede diseñar código para que funcione con el sistema de seguridad.  
  
## <a name="securing-resource-access"></a>Protección de acceso a los recursos  
 Al diseñar y escribir el código, debe proteger y limitar el acceso del código a los recursos, especialmente cuando se usa o se invoca código de origen desconocido. Por lo tanto, tenga en cuenta las siguientes técnicas para asegurarse de que el código sea seguro:  
  
-   No utilice la seguridad de acceso del código (CAS).  
  
-   No utilice el código de confianza parcial.  
  
-   No utilice .NET Remoting.  
  
-   No utilice el modelo de objetos de componente distribuido (DCOM).  
  
-   No utilice los formateadores binarios.  
  
 La seguridad de acceso de código y el código transparente de seguridad no se admitirán como límites de seguridad con código de confianza parcial. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas. Las medidas de seguridad alternativas son:  
  
-   Virtualización  
  
-   AppContainers  
  
-   Usuarios y permisos de sistema operativo (SO)  
  
-   Contenedores de Hyper-V  
  
## <a name="security-neutral-code"></a>Código neutral respecto a la seguridad  
 El código neutral respecto a la seguridad no hace nada explícito con el sistema de seguridad. Se ejecuta con los permisos que recibe. Aunque las aplicaciones que no pudieron detectar las excepciones de seguridad asociadas a operaciones protegidas (como el uso de archivos, las redes etc.) pueden generar una excepción no controlada, el código neutral respecto a la seguridad todavía aprovecha las tecnologías de seguridad de .NET Framework.  
  
 Una biblioteca neutral respecto a la seguridad tiene características especiales que debe conocer. Supongamos que la biblioteca ofrece elementos de la API que usan archivos o llaman a código no administrado; si el código no tiene el permiso correspondiente, no se ejecutará como se describe. Sin embargo, incluso si el código tiene el permiso, cualquier código de aplicación que le llame debe tener el mismo permiso para poder funcionar. Si el código de llamada no tiene el permiso adecuado, un <xref:System.Security.SecurityException> aparece como resultado del recorrido de pila de seguridad de acceso de código.  
  
## <a name="application-code-that-is-not-a-reusable-component"></a>Código de aplicación que no es un componente reutilizable  
 Si el código forma parte de una aplicación a la que no llamará otro código, la seguridad es sencilla y es posible que la codificación especial no sea necesaria. Sin embargo, recuerde que el código malintencionado puede llamar a su código. Aunque la seguridad de acceso a código puede evitar que código malintencionado obtenga acceso a recursos, dicho código todavía podría leer valores de sus campos o propiedades que puedan contener información confidencial.  
  
 Además, si el código acepta la entrada del usuario desde Internet o de otras fuentes no confiables, debe tener cuidado con la entrada malintencionada.  
  
## <a name="managed-wrapper-to-native-code-implementation"></a>Implementación de contenedor administrado en código nativo  
 Normalmente en este escenario se implementa alguna funcionalidad de utilidad en código nativo que quiere que esté disponible para código administrado. Los contenedores administrados son sencillos de escribir mediante la invocación de plataforma o interoperabilidad COM. Sin embargo, si lo hace, los llamadores de los contenedores deben tener derechos de código no administrado para ser correctos. Con la directiva predeterminada, esto significa que el código descargado de una intranet o de Internet no funcionará con los contenedores.  
  
 En lugar de darle a todas las aplicaciones que usan estos contenedores derechos de código no administrado , es mejor dar estos derechos únicamente al código del contenedor. Si la funcionalidad subyacente no expone ningún recurso y la implementación es igual de segura, el contenedor solo necesita imponer sus derechos, lo que permite a cualquier código llamar a través de él. Cuando se trate de recursos, la codificación de seguridad debe ser la mismo que el caso de código de biblioteca descrito en la siguiente sección. Dado que el contenedor puede exponer a los llamadores a esos recursos, se necesita una cuidadosa comprobación de la seguridad del código nativo, lo que es responsabilidad del contenedor.  
  
## <a name="library-code-that-exposes-protected-resources"></a>Código de biblioteca que expone recursos protegidos  
 Este es el enfoque más eficaz y, por tanto, potencialmente peligroso (si se realiza incorrectamente) para la codificación de seguridad: la biblioteca actúa como una interfaz para que otro código obtenga acceso a determinados recursos que no están disponibles de otra manera, de la misma forma que las clases de .NET Framework aplican permisos para los recursos que usan. Siempre que exponga un recurso, su código debe requerir primero el permiso adecuado para el recurso (es decir, debe realizar una comprobación de seguridad) y luego declarar sus derechos para llevar a cabo la operación real.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Proteger los datos de estado](../../../docs/standard/security/securing-state-data.md)|Se describe cómo proteger los miembros privados.|  
|[Seguridad e introducción de datos por el usuario](../../../docs/standard/security/security-and-user-input.md)|Se describen cuestiones de seguridad para las aplicaciones que aceptan la entrada del usuario.|  
|[Seguridad y condiciones de carrera](../../../docs/standard/security/security-and-race-conditions.md)|Se describe cómo evitar condiciones de anticipación en el código.|  
|[Seguridad y generación de código inmediata](../../../docs/standard/security/security-and-on-the-fly-code-generation.md)|Se describen cuestiones de seguridad para las aplicaciones que generan código dinámico.|  
|[Seguridad basada en roles](../../../docs/standard/security/role-based-security.md)|Se describe detalladamente la seguridad basada en roles de .NET Framework y se ofrecen instrucciones para usarla en el código.|
