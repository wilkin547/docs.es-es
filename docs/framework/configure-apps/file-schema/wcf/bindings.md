---
description: 'Más información acerca de: <bindings>'
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: 2cf5b42b8478e34a528cd36435023cac62bf0c1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639385"
---
# \<bindings>

Puede usar el `bindings` elemento para configurar una colección de enlaces estándar y personalizados para Windows Communication Foundation (WCF). Cada entrada es un elemento `binding` que se puede identificar por su `name` único. Los servicios usan los enlaces vinculándose a ellos mediante `name`. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).

## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema

Los enlaces proporcionados por el sistema ocultan la complejidad de la pila de mensajería de WCF. Las aplicaciones que utilizan los enlaces proporcionados por el sistema no requieren el control completo sobre la pila. Los atributos expuestos en cada enlace proporcionado por el sistema son los más apropiados para el escenario de uso de las direcciones de enlace.

La sección de configuración para cada enlace proporcionado por el sistema puede definir varias configuraciones utilizadas para configurar el enlace. Un nombre único identifica a cada configuración.

No es posible agregar elementos o atributos a un enlace proporcionado por el sistema. Para ello, debe implementar un enlace personalizado como se describe en la sección de [enlaces personalizados](#custom-bindings) . Es posible definir un enlace personalizado que imite perfectamente un enlace proporcionado por el sistema y agrega algunos valores en los que la aplicación de usuario desea tener el control.  

Para obtener una lista de los enlaces proporcionados por el sistema, consulte [enlaces proporcionados por el sistema](../../../wcf/system-provided-bindings.md).

## <a name="custom-bindings"></a>Enlaces personalizados

Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF. Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila. Cada elemento define y configura un elemento de la pila. Debe haber un único elemento de `transport` en cada enlace personalizado. Sin este elemento, la pila de la mensajería está incompleta.

El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje. El orden requerido de elementos de pila es el siguiente:  

1. Transacciones (opcional)  

2. Mensajería de confianza (opcional)  

3. Seguridad (opcional)  

4. Codificador  

5. Transporte  

 Los enlaces personalizados se identifican mediante su atributo `name`. Para obtener más información sobre los enlaces personalizados, vea [enlaces personalizados](../../../wcf/extending/custom-bindings.md).

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [Enlaces](../../../wcf/bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
