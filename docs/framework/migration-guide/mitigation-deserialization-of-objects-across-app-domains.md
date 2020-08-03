---
title: 'Mitigación: Deserialización de objetos en distintos dominios de aplicación'
description: Aprenda a diagnosticar y mitigar un problema en el que un intento de deserializar objetos en el contexto de una llamada lógica entre dominios de aplicación produce una excepción.
ms.date: 03/30/2017
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
ms.openlocfilehash: 20ea0f2f0b49000b7d1993adb583a803d9f5be6c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475247"
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a>Mitigación: deserialización de objetos en distintos dominios de aplicación
En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.  
  
## <a name="diagnosing-the-issue"></a>Diagnóstico del problema  
 El problema se produce bajo la secuencia siguiente de condiciones:  
  
1. Una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación.  
  
2. Algunos tipos se agregan explícitamente a la clase <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> llamando a métodos como <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> o <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>. Estos tipos no están marcados como serializables y no se almacenan en la caché global de ensamblados.  
  
3. Después, el código que se ejecuta en el dominio de aplicación no predeterminado intenta leer un valor de un archivo de configuración o usar XML para deserializar un objeto.  
  
4. Para leer de un archivo de configuración o deserializar el objeto, un objeto <xref:System.Xml.XmlReader> intenta tener acceso al sistema de configuración.  
  
5. Si aún no se ha inicializado el sistema de configuración, deberá completarse dicha inicialización. Esto significa, entre otras cosas, que el runtime tiene que crear una ruta de acceso estable para un sistema de configuración, lo que hace de la forma siguiente:  
  
    1. Busca evidencia para el dominio de aplicación no predeterminado.  
  
    2. Intenta calcular la evidencia para el dominio de aplicación no predeterminado basándose en el dominio de aplicación predeterminado.  
  
    3. La llamada para obtener evidencia del dominio de aplicación predeterminado desencadena una llamada de dominio de aplicación cruzado desde el dominio de aplicación no predeterminado al dominio de aplicación predeterminado.  
  
    4. Como parte del contrato de dominio de aplicación cruzado de .NET Framework, el contenido del contexto de llamada lógico también tiene que calcularse en los límites de dominio de aplicación.  
  
6. Dado que los tipos incluidos en el contexto de llamada lógico no se pueden resolver en el dominio de aplicación predeterminado, se produce una excepción.  
  
## <a name="mitigation"></a>Mitigación  
 Para solucionar este problema, haga lo siguiente  
  
1. Busque la llamada a `get_Evidence` en la pila de llamadas cuando se produce la excepción. La excepción puede ser cualquiera de las existentes en un gran subconjunto de excepciones, incluidas <xref:System.IO.FileNotFoundException> y <xref:System.Runtime.Serialization.SerializationException>.  
  
2. Identifique el lugar de la aplicación donde no se agrega ningún objeto al contexto de llamada lógico y agregue el código siguiente:  
  
    ```csharp
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
