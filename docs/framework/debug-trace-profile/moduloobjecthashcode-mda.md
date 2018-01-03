---
title: MDA de moduloObjectHashcode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 618196473e8e947e84b0506771bce84ee71a1c2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="moduloobjecthashcode-mda"></a>MDA de moduloObjectHashcode
El Asistente para la depuración administrada (MDA) `moduloObjectHashcode` cambia el comportamiento de la clase <xref:System.Object> para realizar una operación de módulo en el código hash devuelto por el método <xref:System.Object.GetHashCode%2A>. El módulo predeterminado para este MDA es 1, lo que hace que <xref:System.Object.GetHashCode%2A> devuelva 0 para todos los objetos.  
  
## <a name="symptoms"></a>Síntomas  
 Después de moverlo a una nueva versión de Common Language Runtime (CLR), un programa ya no se ejecuta correctamente:  
  
-   El programa está recibiendo el objeto equivocado desde una <xref:System.Collections.Hashtable>.  
  
-   El orden de enumeración de una <xref:System.Collections.Hashtable> tiene un cambio que interrumpe el programa.  
  
-   Dos objetos que solían ser iguales ya no lo son.  
  
-   Dos objetos que solían ser no iguales ahora lo son.  
  
## <a name="cause"></a>Motivo  
 El programa puede estar recibiendo el objeto equivocado desde <xref:System.Collections.Hashtable> porque la implementación del método <xref:System.Object.Equals%2A> en la clase para la clave en <xref:System.Collections.Hashtable> comprueba la igualdad de objetos al comparar los resultados de la llamada al método <xref:System.Object.GetHashCode%2A>. No deben usarse códigos hash para comprobar la igualdad de objetos porque dos objetos pueden tener el mismo código hash incluso si sus respectivos campos tienen valores diferentes. Estas colisiones de código hash, aunque sean poco frecuentes en la práctica, se producen. El efecto que tiene en una búsqueda de <xref:System.Collections.Hashtable> es que dos claves que no son iguales parecen iguales, y se devuelve el objeto incorrecto de la <xref:System.Collections.Hashtable>. Por motivos de rendimiento, la implementación de <xref:System.Object.GetHashCode%2A> puede cambiar entre las versiones del tiempo de ejecución, por lo que es posible que en una versión se produzcan conflictos que no aparezcan en versiones posteriores. Habilite este MDA para probar si el código tiene errores cuando se producen colisiones de códigos hash. Cuando está habilitado, este MDA hace que el método <xref:System.Object.GetHashCode%2A> devuelva un valor 0, lo que provoca que todos los códigos hash colisionen. El único efecto que debería tener la habilitación de este MDA en el programa es que se ejecute más lentamente.  
  
 El orden de enumeración de una <xref:System.Collections.Hashtable> puede cambiar de una versión del tiempo de ejecución a otra si cambia el algoritmo que se usa para calcular los códigos hash para la clave. Para comprobar si el programa ha tomado una dependencia en el orden de enumeración de claves o valores fuera de una tabla hash, puede habilitar este MDA.  
  
## <a name="resolution"></a>Resolución  
 Nunca use códigos hash como sustitutos de la identidad de objetos. Implemente la invalidación del método <xref:System.Object.Equals%2A?displayProperty=nameWithType> para no comparar códigos hash.  
  
 No cree dependencias en el orden de las enumeraciones de claves o valores en tablas hash.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Las aplicaciones se ejecutan más despacio cuando se habilita este MDA. Este MDA simplemente toma el código hash que se habría devuelto y, en su lugar, devuelve el resto cuando se divide por un módulo.  
  
## <a name="output"></a>Salida  
 No hay ningún resultado para este MDA.  
  
## <a name="configuration"></a>Configuración  
 El atributo `modulus` especifica el módulo que se usa en el código hash. El valor predeterminado es 1.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.Equals%2A?displayProperty=nameWithType>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
