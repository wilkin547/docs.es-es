---
title: "Using Libraries from Partially Trusted Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], partially trusted code"
  - "partially trusted code"
  - "partial trust"
  - "AllowPartiallyTrustedCallersAttribute attribute"
  - "code access security, partially trusted code"
  - "APTCA"
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
caps.latest.revision: 25
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 23
---
# Using Libraries from Partially Trusted Code
> [!NOTE]
>  En este tema se trata el comportamiento de los ensamblados con nombre seguro, que solo se aplica a los ensamblados de [nivel 1](../../../docs/framework/misc/security-transparent-code-level-1.md). Los ensamblados [Security\-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] o una versión posterior no se ven afectados por los nombres seguros. Para más información sobre los cambios realizados en el sistema de seguridad, consulte [Cambios de seguridad](../../../docs/framework/security/security-changes.md).  
  
> [!CAUTION]
>  Seguridad de acceso del código y código de confianza parcial  
>   
>  .NET Framework proporciona seguridad de acceso del código \(CAS\), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.  La seguridad de acceso del código en .NET Framework no debe usarse como límite de seguridad para código de confianza parcial, especialmente si se trata de código de origen desconocido. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.  
>   
>  Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.  
  
 Las aplicaciones que reciben menos de la plena confianza de su host o espacio aislado no pueden llamar a las bibliotecas administradas compartidas a menos que el escritor de la biblioteca se lo permita específicamente mediante el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Por lo tanto, los escritores de aplicaciones deben tener en cuenta que habrá algunas bibliotecas que no estarán a su disposición desde un contexto de confianza parcial. De forma predeterminada, el código ejecutado en un [espacio aislado](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) de confianza parcial y que no está en la lista de ensamblados de plena confianza tendrá una confianza parcial. Si no espera que el código se ejecute desde un contexto de confianza parcial o que lo llame un código de confianza parcial, no tiene que preocuparse de la información de esta sección. Sin embargo, si escribe un código que debe interactuar con un código de confianza parcial o que debe funcionar desde un contexto de confianza parcial, debe considerar los siguientes factores:  
  
-   Las bibliotecas deben firmarse con un nombre seguro para que las puedan compartir varias aplicaciones. Los nombres seguros permiten que el código se coloque en la caché global de ensamblados o se agregue a la lista de plena confianza de un espacio aislado <xref:System.AppDomain>, de manera que los consumidores puedan comprobar que un determinado fragmento del código móvil proviene de usted.  
  
-   De forma predeterminada, las bibliotecas compartidas de [nivel 1](../../../docs/framework/misc/security-transparent-code-level-1.md) con nombre seguro efectúan un [LinkDemand](../../../docs/framework/misc/link-demands.md) implícito para obtener automáticamente una confianza completa, sin que el escritor de la biblioteca tenga que hacer nada.  
  
-   Si un llamador no tiene plena confianza y, aun así, intenta llamar a dicha biblioteca, el tiempo de ejecución produce una <xref:System.Security.SecurityException>, de manera que el llamador no podrá vincularse a la biblioteca.  
  
-   Para deshabilitar el **LinkDemand** automático y evitar que se produzca la excepción, puede colocar el atributo **AllowPartiallyTrustedCallersAttribute** en el ámbito de ensamblado de una biblioteca compartida. Este atributo permite llamar a las bibliotecas desde un código administrado de confianza parcial.  
  
-   El código de confianza parcial al que se concede acceso a una biblioteca con este atributo sigue estando sujeto a otras restricciones definidas por el <xref:System.AppDomain>.  
  
-   No hay ningún mecanismo de programación que permita que el código de confianza parcial llame a una biblioteca que no tenga el atributo **AllowPartiallyTrustedCallersAttribute** .  
  
 Las bibliotecas que son privadas para una aplicación específica no necesitan un nombre seguro ni el atributo **AllowPartiallyTrustedCallersAttribute**; además, no se les puede hacer referencia mediante código potencialmente malintencionado fuera de la aplicación. Este código está protegido contra el uso indebido intencional o involuntario por parte del código móvil de confianza parcial sin que el desarrollador tenga que hacer nada más.  
  
 Considere la posibilidad de habilitar de forma explícita el uso por parte de un código de confianza parcial en los siguientes tipos de código:  
  
-   Código en el que se han probado minuciosamente las vulnerabilidades de seguridad y que cumple las directrices descritas en [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md).  
  
-   Bibliotecas de código con nombre seguro escritas específicamente para escenarios de confianza parcial.  
  
-   Cualquier componente \(ya sea de confianza parcial o de plena confianza\) firmado con un nombre seguro, llamado mediante el código descargado de Internet.  
  
> [!NOTE]
>  Algunas clases de la biblioteca de clases de .NET Framework no tienen el atributo **AllowPartiallyTrustedCallersAttribute** y no se pueden llamar mediante código de confianza parcial.  
  
## Vea también  
 [Code Access Security](../../../docs/framework/misc/code-access-security.md)