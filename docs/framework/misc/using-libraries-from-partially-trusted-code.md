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
ms.openlocfilehash: 6836d6c7f67afba316125b57b2c3e64a59ac648f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216986"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Utilizar bibliotecas de código que no es de plena confianza
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
> En este tema se trata el comportamiento de los ensamblados con nombre seguro y se aplica solo a los ensamblados de [nivel 1](security-transparent-code-level-1.md) . El [código transparente en seguridad,](security-transparent-code-level-2.md) los ensamblados de nivel 2 en el .NET Framework 4 o posterior no se ven afectados por los nombres seguros. Para obtener más información acerca de los cambios en el sistema de seguridad, consulte [cambios de seguridad](../security/security-changes.md).  
  
 Las aplicaciones que reciben menos de la plena confianza de su host o espacio aislado no pueden llamar a las bibliotecas administradas compartidas a menos que el escritor de la biblioteca se lo permita específicamente mediante el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Por lo tanto, los escritores de aplicaciones deben tener en cuenta que habrá algunas bibliotecas que no estarán a su disposición desde un contexto de confianza parcial. De forma predeterminada, todo el código que se ejecuta en un [espacio aislado](how-to-run-partially-trusted-code-in-a-sandbox.md) de confianza parcial y no está en la lista de ensamblados de plena confianza es de confianza parcial. Si no espera que el código se ejecute desde un contexto de confianza parcial o que lo llame un código de confianza parcial, no tiene que preocuparse de la información de esta sección. Sin embargo, si escribe un código que debe interactuar con un código de confianza parcial o que debe funcionar desde un contexto de confianza parcial, debe considerar los siguientes factores:  
  
- Las bibliotecas deben firmarse con un nombre seguro para que las puedan compartir varias aplicaciones. Los nombres seguros permiten que el código se coloque en la caché global de ensamblados o se agregue a la lista de plena confianza de un espacio aislado <xref:System.AppDomain>, de manera que los consumidores puedan comprobar que un determinado fragmento del código móvil proviene de usted.  
  
- De forma predeterminada, las bibliotecas compartidas de [nivel 1](security-transparent-code-level-1.md) con nombre seguro realizan una [LinkDemand](link-demands.md) implícita para la plena confianza automáticamente, sin que el escritor de la biblioteca tenga que hacer nada.  
  
- Si un llamador no tiene plena confianza y, aun así, intenta llamar a dicha biblioteca, el tiempo de ejecución produce una <xref:System.Security.SecurityException>, de manera que el llamador no podrá vincularse a la biblioteca.  
  
- Para deshabilitar el **LinkDemand** automático e impedir que se produzca la excepción, puede colocar el atributo **AllowPartiallyTrustedCallersAttribute** en el ámbito de ensamblado de una biblioteca compartida. Este atributo permite llamar a las bibliotecas desde un código administrado de confianza parcial.  
  
- El código de confianza parcial al que se concede acceso a una biblioteca con este atributo sigue estando sujeto a otras restricciones definidas por el <xref:System.AppDomain>.  
  
- No hay ninguna forma mediante programación para que el código de confianza parcial llame a una biblioteca que no tenga el atributo **AllowPartiallyTrustedCallersAttribute** .  
  
 Las bibliotecas que son privadas para una aplicación específica no requieren un nombre seguro ni el atributo **AllowPartiallyTrustedCallersAttribute** y no es posible hacer referencia a ellas desde código potencialmente malintencionado fuera de la aplicación. Este código está protegido contra el uso indebido intencional o involuntario por parte del código móvil de confianza parcial sin que el desarrollador tenga que hacer nada más.  
  
 Considere la posibilidad de habilitar de forma explícita el uso por parte de un código de confianza parcial en los siguientes tipos de código:  
  
- Código que se ha probado diligentemente en busca de vulnerabilidades de seguridad y cumple las directrices descritas en [instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md).  
  
- Bibliotecas de código con nombre seguro escritas específicamente para escenarios de confianza parcial.  
  
- Cualquier componente (ya sea de confianza parcial o de plena confianza) firmado con un nombre seguro, llamado mediante el código descargado de Internet.  
  
> [!NOTE]
> Algunas clases de la biblioteca de clases de .NET Framework no tienen el atributo **AllowPartiallyTrustedCallersAttribute** y el código de confianza parcial no puede llamarlas.  
  
## <a name="see-also"></a>Consulte también

- [Seguridad de acceso del código](code-access-security.md)
