---
title: Instrucciones de programación segura para código sin administrar
ms.date: 03/30/2017
helpviewer_keywords:
- code security, unmanaged code
- unmanaged code, securing
- security [.NET Framework], unmanaged code
- secure coding, unmanaged code
ms.assetid: a8d15139-d368-4c9c-a747-ba757781117c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60e293ac8c9100876aa5a524bb5dda04e9f4183f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="secure-coding-guidelines-for-unmanaged-code"></a>Instrucciones de programación segura para código sin administrar
El código de algunas bibliotecas necesita llamar a código no administrado (por ejemplo, las API de código nativo, como Win32). Como esto implica salir del perímetro de seguridad del código administrado, se requiere mucha precaución. Si el código es neutro en cuanto a seguridad, tanto su código como cualquier otro código que lo llame deberán tener permiso de código no administrado (<xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> especificada).  
  
 Sin embargo, a menudo sucede que es absurdo conceder al llamador permisos tan amplios. En esos casos, el código de confianza puede actuar como intermediario, de forma similar al contenedor administrado o el código de biblioteca que se describen en [Proteger código de contenedor](../../../docs/framework/misc/securing-wrapper-code.md). Si la funcionalidad del código no administrado subyacente es totalmente segura, se puede exponer directamente. Si no, es necesario realizar primero la comprobación (solicitud) de permisos correspondiente.  
  
 Si su código llama a código no administrado, pero no quiere exigir que los llamadores tengan permiso para acceder a código no administrado, debe declarar este derecho con una aserción. Las aserciones bloquean el recorrido de la pila en su marco. Debe tener cuidado de no crear una vulnerabilidad de seguridad en este proceso. Normalmente, para esto es necesario solicitar un permiso adecuado a los llamadores y, luego, utilizar código no administrado para realizar solamente lo que permite el permiso y nada más. En algunos casos (por ejemplo, una función get time-of-day), el código no administrado se puede exponer directamente a los llamadores sin ninguna comprobación de seguridad. En cualquier caso, todo el código que se declare con aserciones debe asumir la responsabilidad de mantener la seguridad.  
  
 Dado que cualquier código administrado que proporcione una ruta de acceso al código nativo es un posible objetivo de códigos malintencionados, deberá tener mucho cuidado cuando decida qué código no administrado se puede usar de forma segura y cómo se debe usar. Por lo general, el código no administrado nunca debe exponerse directamente a llamadores de confianza parcial. Al evaluar la seguridad del uso de código no administrado en las bibliotecas a las que puede llamar el código de confianza parcial, hay dos aspectos que se deben tener en cuenta:  
  
-   **Funcionalidad**. ¿La API no administrada proporciona funcionalidad que no permita a los llamadores realizar operaciones potencialmente peligrosas? La seguridad de acceso del código utiliza permisos para exigir el acceso a los recursos, por lo que debe tener en cuenta si la API utiliza archivos, una interfaz de usuario o subprocesos, o si expone información protegida. Si es así, el ajuste del código administrado debe solicitar los permisos necesarios para poder escribir dicho código. Además, aunque no esté protegido con un permiso, el acceso a la memoria debe limitarse a la seguridad de tipo estricto.  
  
-   **Comprobación de parámetros**. Un ataque habitual consiste en pasar parámetros inesperados a métodos de la API de código no administrado que están expuestos, en un intento de hacer que funcionen de manera distinta a su especificación. Las saturaciones del búfer con índices externos al intervalo o valores de desplazamiento son un ejemplo común de este tipo de ataque, al igual que los parámetros que podrían aprovechar un error en el código subyacente. Por lo tanto, aunque la API de código no administrado sea segura funcionalmente (después de las solicitudes necesarias) para los llamadores de confianza parcial, el código administrado también debe comprobar la validez de los parámetros de manera exhaustiva, para asegurarse de que el código malintencionado no pueda realizar llamadas no previstas con el nivel del contenedor de código administrado.  
  
## <a name="using-suppressunmanagedcodesecurityattribute"></a>Utilizar SuppressUnmanagedCodeSecurityAttribute  
 Hay un aspecto del rendimiento que está relacionado con la aserción y la posterior llamada a código no administrado. Por cada llamada de este tipo, el sistema de seguridad solicita permiso automáticamente al código no administrado, lo que provoca un recorrido de la pila cada vez. Si declara una aserción y, justo después, llama a código no administrado, puede que el recorrido de la pila no tenga sentido: estará formado por su aserción y su llamada a código no administrado.  
  
 Se puede aplicar un atributo personalizado denominado <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> a los puntos de entrada del código no administrado para deshabilitar la comprobación de seguridad normal que solicita <xref:System.Security.Permissions.SecurityPermission> con el permiso <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> especificado. Es necesario extremar las precauciones siempre que se haga esto, porque esta acción abre la puerta al código no administrado sin comprobaciones de seguridad en tiempo de ejecución. Se debe tener en cuenta que, incluso si se aplica **SuppressUnmanagedCodeSecurityAttribute** , hay una comprobación de seguridad que se realiza una sola vez durante la compilación Just-In-Time (JIT), con el fin de comprobar que el llamador inmediato tiene permiso para llamar a código no administrado.  
  
 Si utiliza el **SuppressUnmanagedCodeSecurityAttribute**, compruebe los puntos siguientes:  
  
-   Haga que el punto de entrada al código no administrado sea interno o inaccesible fuera de su código.  
  
-   Todas las llamadas a código no administrado son vulnerabilidades de seguridad potenciales. Asegúrese de que su código no sea una puerta de entrada que permita al código malintencionado llamar indirectamente a código no administrado y evitar comprobaciones de seguridad. Solicite permisos, si es adecuado.  
  
-   Use una convención de nomenclatura que identifique explícitamente el momento en el que crea una ruta de acceso peligrosa a código no administrado, como se describe en la siguiente sección.  
  
## <a name="naming-convention-for-unmanaged-code-methods"></a>Convención de nomenclatura para métodos de código no administrado  
 Hay una convención establecida, útil y muy recomendada, para asignar nombres a los métodos de código no administrado. Todos los métodos de código no administrado se dividen en tres categorías: **safe**, **native**y **unsafe**. Estas palabras clave se pueden utilizar como nombres de clases, dentro de las cuales se definen los distintos tipos de puntos de entrada de código no administrado. En el código fuente, estas palabras clave se deben agregar al nombre de la clase, como en `Safe.GetTimeOfDay`, `Native.Xyz`o `Unsafe.DangerousAPI`, por ejemplo. Cada una de estas palabras clave proporciona información de seguridad útil para los desarrolladores que utilizan esa clase, como se describe en la tabla siguiente.  
  
|Palabra clave|Consideraciones de seguridad|  
|-------------|-----------------------------|  
|**safe**|Totalmente inofensivo cuando lo llama cualquier código, aunque sea código malintencionado. Se puede usar como cualquier otro código administrado. Por ejemplo, las funciones que obtienen la hora del día suelen ser seguras.|  
|**native**|Neutro en cuanto a seguridad: es decir, código no administrado que requiere permiso para llamar a código no administrado. Se comprueba la seguridad, lo que detiene a los llamadores no autorizados.|  
|**unsafe**|Punto de entrada de código no administrado potencialmente peligroso sin seguridad. Los desarrolladores deben extremar las precauciones cuando utilicen este tipo de código no administrado, y asegurarse de aplicar otras protecciones para evitar vulnerabilidades de seguridad. Los desarrolladores deben actuar con responsabilidad, ya que esta palabra clave invalida el sistema de seguridad.|  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)
