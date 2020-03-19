---
title: Directrices de codificación segura para .NET
description: Código de diseño con el que trabajar . Permisos forzados por NET y otra aplicación para ayudar a evitar que el código malintencionado acceda a los datos o realice otras acciones.
ms.date: 06/28/2018
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET], security
- code security, options
- security-neutral code
- security [.NET], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
ms.openlocfilehash: 05f7e039ecdc0cd33baa015872924fb9e1f078aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187723"
---
# <a name="secure-coding-guidelines"></a>Directrices de codificación segura

La seguridad basada en pruebas y la seguridad de acceso por código ofrecen mecanismos explícitos y muy eficaces para implementar la seguridad. La mayoría del código de aplicación simplemente puede usar la infraestructura implementada por .NET. En algunos casos, se requiere la seguridad específica de aplicación adicional, creada ampliando el sistema de seguridad o mediante nuevos métodos ad hoc.

Con los permisos forzados de .NET y otras aplicaciones en el código, debe levantar barreras para evitar que el código malintencionado tenga acceso a información que no desea que tenga o realice otras acciones no deseadas. Además, debe lograr un equilibrio entre la seguridad y la facilidad de uso en todos los escenarios esperados mediante código de confianza.

Esta información general describe las diferentes formas en que se puede diseñar código para que funcione con el sistema de seguridad.

## <a name="securing-resource-access"></a>Protección del acceso a los recursos

Al diseñar y escribir el código, debe proteger y limitar el acceso del código a los recursos, especialmente cuando se usa o se invoca código de origen desconocido. Por lo tanto, tenga en cuenta las siguientes técnicas para asegurarse de que el código sea seguro:

- No utilice la seguridad de acceso del código (CAS).

- No utilice el código de confianza parcial.

- No utilice el atributo [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) (APTCA).

- No utilice .NET Remoting.

- No utilice el modelo de objetos de componente distribuido (DCOM).

- No utilice los formateadores binarios.

La seguridad de acceso de código y el código transparente de seguridad no se admiten como límite de seguridad con código de confianza parcial. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas. Las medidas de seguridad alternativas son:

- Virtualización

- AppContainers

- Usuarios y permisos de sistema operativo (SO)

- Contenedores de Hyper-V

## <a name="security-neutral-code"></a>Código de seguridad neutral

El código neutral respecto a la seguridad no hace nada explícito con el sistema de seguridad. Se ejecuta con los permisos que recibe. Aunque las aplicaciones que no detectan las excepciones de seguridad asociadas con operaciones protegidas (como el uso de archivos, redes, etc.) pueden dar lugar a una excepción no controlada, el código neutro en seguridad sigue aprovechando las tecnologías de seguridad de .NET .

Una biblioteca neutral respecto a la seguridad tiene características especiales que debe conocer. Supongamos que la biblioteca proporciona elementos de API que usan archivos o llaman a código no administrado. Si el código no tiene el permiso correspondiente, no se ejecutará como se describe. Sin embargo, incluso si el código tiene el permiso, cualquier código de aplicación que le llame debe tener el mismo permiso para poder funcionar. Si el código de llamada no tiene <xref:System.Security.SecurityException> el permiso correcto, aparece un como resultado del recorrido de la pila de seguridad de acceso de código.

## <a name="application-code-that-isnt-a-reusable-component"></a>Código de aplicación que no es un componente reutilizable

Si el código forma parte de una aplicación a la que no llamará otro código, la seguridad es sencilla y es posible que no se requiera una codificación especial. Sin embargo, recuerde que el código malintencionado puede llamar a su código. Aunque la seguridad de acceso a código puede evitar que código malintencionado obtenga acceso a recursos, dicho código todavía podría leer valores de sus campos o propiedades que puedan contener información confidencial.

Además, si el código acepta la entrada del usuario desde Internet o de otras fuentes no confiables, debe tener cuidado con la entrada malintencionada.

## <a name="managed-wrapper-to-native-code-implementation"></a>Contenedor administrado para la implementación de código nativo

Normalmente en este escenario se implementa alguna funcionalidad de utilidad en código nativo que quiere que esté disponible para código administrado. Los contenedores administrados son sencillos de escribir mediante la invocación de plataforma o interoperabilidad COM. Sin embargo, si lo hace, los llamadores de los contenedores deben tener derechos de código no administrado para ser correctos. En la directiva predeterminada, esto significa que el código descargado de una intranet o Internet no funcionará con los contenedores.

En lugar de conceder derechos de código no administrado a todas las aplicaciones que usan estos contenedores, es mejor conceder estos derechos solo al código contenedor. Si la funcionalidad subyacente no expone ningún recurso y la implementación es igual de segura, el contenedor solo necesita imponer sus derechos, lo que permite a cualquier código llamar a través de él. Cuando se trate de recursos, la codificación de seguridad debe ser la mismo que el caso de código de biblioteca descrito en la siguiente sección. Dado que el contenedor puede exponer a los llamadores a esos recursos, se necesita una cuidadosa comprobación de la seguridad del código nativo, lo que es responsabilidad del contenedor.

## <a name="library-code-that-exposes-protected-resources"></a>Código de biblioteca que expone recursos protegidos

El siguiente enfoque es el más eficaz y, por lo tanto, potencialmente peligroso (si se hace incorrectamente) para la codificación de seguridad: la biblioteca sirve como interfaz para que otro código tenga acceso a determinados recursos que de otro modo no están disponibles, del igual que las clases .NET aplican la aplicación de la aplicación. permisos para los recursos que utilizan. Siempre que exponga un recurso, su código debe requerir primero el permiso adecuado para el recurso (es decir, debe realizar una comprobación de seguridad) y luego declarar sus derechos para llevar a cabo la operación real.

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----------|-----------------|
|[Proteger los datos de estado](securing-state-data.md)|Se describe cómo proteger los miembros privados.|
|[Seguridad e introducción de datos por el usuario](security-and-user-input.md)|Se describen cuestiones de seguridad para las aplicaciones que aceptan la entrada del usuario.|
|[Seguridad y condiciones de carrera](security-and-race-conditions.md)|Se describe cómo evitar condiciones de anticipación en el código.|
|[Seguridad y generación de código inmediata](security-and-on-the-fly-code-generation.md)|Se describen cuestiones de seguridad para las aplicaciones que generan código dinámico.|
|[Seguridad basada en roles](role-based-security.md)|Describe detalladamente la seguridad basada en roles de .NET y proporciona instrucciones para usarla en el código.|
