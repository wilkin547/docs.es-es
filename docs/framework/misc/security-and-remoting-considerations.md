---
title: Consideraciones de seguridad y de interacción remota
ms.date: 03/30/2017
helpviewer_keywords:
- code security, remoting
- remoting, security
- security [.NET Framework], remoting
- secure coding, remoting
ms.assetid: 125d2ab8-55a4-4e5f-af36-a7d401a37ab0
ms.openlocfilehash: 7a56c9894da88382f40dcd475e89776a83a59322
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215782"
---
# <a name="security-and-remoting-considerations"></a>Consideraciones de seguridad y de interacción remota
La comunicación remota permite configurar llamadas transparentes entre dominios de aplicación, procesos o equipos. Sin embargo, el recorrido de la pila de seguridad de acceso del código no puede cruzar los límites de los procesos o equipos (se aplica entre dominios de aplicación del mismo proceso).  
  
 Las clases que se pueden usar de forma remota (derivadas de una clase <xref:System.MarshalByRefObject>) deben asumir la responsabilidad de la seguridad. El código debe usarse solo en entornos cerrados donde el código llamador puede ser de confianza de forma implícita, o las llamadas remotas deben diseñarse de modo que no sometan el código protegido a entradas externas que pudieran usarlo de forma malintencionada.  
  
 Por lo general, nunca debe exponer métodos, propiedades o eventos protegidos por [LinkDemand](link-demands.md) declarativo y <xref:System.Security.Permissions.SecurityAction.InheritanceDemand> comprobaciones de seguridad. Con la comunicación remota, estas comprobaciones no se fuerzan. Otras comprobaciones de seguridad, como <xref:System.Security.Permissions.SecurityAction.Demand>, [Assert](using-the-assert-method.md), etc., funcionan entre dominios de aplicación dentro de un proceso, pero no funcionan en escenarios entre procesos o entre equipos.  
  
## <a name="protected-objects"></a>Objetos protegidos  
 Algunos objetos contienen un estado de seguridad en sí mismos. Estos objetos no se deben pasar a código que no sea de confianza, porque este adquiriría una autorización de seguridad más allá de sus propios permisos.  
  
 Un ejemplo es la creación de un objeto <xref:System.IO.FileStream>. <xref:System.Security.Permissions.FileIOPermission> se solicita en el momento de la creación y, si se realiza correctamente, se devuelve el objeto de archivo. Sin embargo, si esta referencia de objeto se pasa al código sin los permisos de archivo, el objeto podrá leer y escribir este archivo en particular.  
  
 La defensa más sencilla para este tipo de objeto es solicitar el mismo **FileIOPermission** de cualquier código que intente obtener la referencia de objeto a través de un elemento de la API pública.  
  
## <a name="application-domain-crossing-issues"></a>Problemas de cruce entre dominios de aplicaciones  
 Para aislar código en entornos de hospedaje administrado, es habitual generar varios dominios de aplicación secundarios con directiva explícita para reducir los niveles de permiso para varios ensamblados. Sin embargo, la directiva de estos ensamblados no cambia en el dominio de aplicación predeterminado. Si uno de los dominios de aplicación secundarios puede forzar que el dominio de aplicación predeterminado cargue un ensamblado, se pierde el efecto de aislamiento del código y los tipos del ensamblado cargado forzosamente podrán ejecutar código en un nivel de confianza más alto.  
  
 Un dominio de aplicación puede forzar que otro dominio de aplicación cargue un ensamblado y ejecute el código contenido en él llamando a un proxy a un objeto hospedado en el otro dominio de aplicación. Para obtener un proxy de dominio entre aplicaciones, el dominio de aplicación que hospeda el objeto debe distribuir uno mediante un valor devuelto o un parámetro de llamada a método. O bien, si acaba de crear el dominio de aplicación, el creador tiene un proxy al objeto <xref:System.AppDomain> de forma predeterminada. Por lo tanto, para evitar romper el aislamiento del código, un dominio de aplicación con un nivel de confianza mayor no debe distribuir referencias a objetos con cálculo de referencias por referencia (instancias de clases derivadas de <xref:System.MarshalByRefObject>) en su dominio a dominios de aplicación con niveles de confianza inferiores.  
  
 Normalmente, el dominio de aplicación predeterminado crea los dominios de aplicación secundarios con un objeto de control en cada uno de ellos. El objeto de control administra el nuevo dominio de aplicación y, en ocasiones, recibe pedidos del dominio de aplicación predeterminado, pero en realidad no puede contactar con el dominio directamente. En ocasiones, el dominio de aplicación predeterminado llama a su proxy al objeto de control. Sin embargo, puede haber casos en los que es necesario que el objeto de control devuelva la llamada al dominio de aplicación predeterminado. En estos casos, el dominio de aplicación predeterminado pasa un objeto de devolución de llamada de serialización por referencia al constructor del objeto de control. Es responsabilidad del objeto de control proteger este proxy. Si el objeto de control coloca el proxy en un campo estático público de una clase pública o expone el proxy públicamente de cualquier otra forma, abriría un mecanismo peligroso para que otro código devuelva la llamada al dominio de aplicación predeterminado. Por este motivo, los objetos de control siempre son de confianza de forma implícita para que el proxy sea privado.  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)
