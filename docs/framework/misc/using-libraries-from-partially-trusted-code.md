---
title: Utilizar bibliotecas de código que no es de plena confianza
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8500abe590d4c85dcb5ecda54212a1ba9cc7950d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586983"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Utilizar bibliotecas de código que no es de plena confianza
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  En este tema trata el comportamiento de los ensamblados con nombre seguro y solo se aplica a [nivel 1](../../../docs/framework/misc/security-transparent-code-level-1.md) ensamblados. [Código transparente en seguridad, nivel 2](../../../docs/framework/misc/security-transparent-code-level-2.md) ensamblados en el [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] o versiones posteriores no se ven afectados por los nombres seguros. Para obtener más información sobre los cambios en el sistema de seguridad, consulte [cambios de seguridad](../../../docs/framework/security/security-changes.md).  
  
 Las aplicaciones que reciben menos de la plena confianza de su host o espacio aislado no pueden llamar a las bibliotecas administradas compartidas a menos que el escritor de la biblioteca se lo permita específicamente mediante el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Por lo tanto, los escritores de aplicaciones deben tener en cuenta que habrá algunas bibliotecas que no estarán a su disposición desde un contexto de confianza parcial. De forma predeterminada, todo el código que se ejecuta en confianza parcial [sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) y no está en la lista de ensamblados de plena confianza es de confianza parcial. Si no espera que el código se ejecute desde un contexto de confianza parcial o que lo llame un código de confianza parcial, no tiene que preocuparse de la información de esta sección. Sin embargo, si escribe un código que debe interactuar con un código de confianza parcial o que debe funcionar desde un contexto de confianza parcial, debe considerar los siguientes factores:  
  
- Las bibliotecas deben firmarse con un nombre seguro para que las puedan compartir varias aplicaciones. Los nombres seguros permiten que el código se coloque en la caché global de ensamblados o se agregue a la lista de plena confianza de un espacio aislado <xref:System.AppDomain>, de manera que los consumidores puedan comprobar que un determinado fragmento del código móvil proviene de usted.  
  
- De forma predeterminada, con nombre seguro [nivel 1](../../../docs/framework/misc/security-transparent-code-level-1.md) bibliotecas compartidas realizan implícita [LinkDemand](../../../docs/framework/misc/link-demands.md) para completo confiar automáticamente, sin que el escritor de la biblioteca tenga que hacer nada.  
  
- Si un llamador no tiene plena confianza y, aun así, intenta llamar a dicha biblioteca, el tiempo de ejecución produce una <xref:System.Security.SecurityException>, de manera que el llamador no podrá vincularse a la biblioteca.  
  
- Para deshabilitar el automático **LinkDemand** y evitar que se produzca la excepción, puede colocar el **AllowPartiallyTrustedCallersAttribute** atributo en el ámbito de ensamblado de un compartido biblioteca. Este atributo permite llamar a las bibliotecas desde un código administrado de confianza parcial.  
  
- El código de confianza parcial al que se concede acceso a una biblioteca con este atributo sigue estando sujeto a otras restricciones definidas por el <xref:System.AppDomain>.  
  
- No hay ningún mecanismo de programación para el código de confianza parcial llame a una biblioteca que no tiene el **AllowPartiallyTrustedCallersAttribute** atributo.  
  
 Las bibliotecas que son privadas para una aplicación específica no requieren un nombre seguro o la **AllowPartiallyTrustedCallersAttribute** atributo y no se puede hacer referencia a código potencialmente malintencionado fuera de la aplicación. Este código está protegido contra el uso indebido intencional o involuntario por parte del código móvil de confianza parcial sin que el desarrollador tenga que hacer nada más.  
  
 Considere la posibilidad de habilitar de forma explícita el uso por parte de un código de confianza parcial en los siguientes tipos de código:  
  
- Código que se han probado minuciosamente las vulnerabilidades de seguridad y cumple las directrices descritas en [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md).  
  
- Bibliotecas de código con nombre seguro escritas específicamente para escenarios de confianza parcial.  
  
- Cualquier componente (ya sea de confianza parcial o de plena confianza) firmado con un nombre seguro, llamado mediante el código descargado de Internet.  
  
> [!NOTE]
>  Algunas clases en la biblioteca de clases de .NET Framework no tienen la **AllowPartiallyTrustedCallersAttribute** atributo y no se puede llamar mediante código de confianza parcial.  
  
## <a name="see-also"></a>Vea también

- [Seguridad de acceso del código](../../../docs/framework/misc/code-access-security.md)
