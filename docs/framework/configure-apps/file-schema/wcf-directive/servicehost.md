---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: fdd6d83836c4ef31a4d7c8e68cb0cc050ac6bea4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787800"
---
# <a name="servicehost"></a>\@ServiceHost

Asocia el generador usado para crear el host del servicio con el servicio que se va a hospedar y otros aspectos de programación necesarios para tener acceso o compilar el código de hospedaje proporcionado en el archivo .svc.

## <a name="syntax"></a>Sintaxis

```xml
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```

## <a name="attributes"></a>Atributos

### <a name="service"></a>Servicio

El nombre del tipo de CLR del servicio hospedado. Esto debería ser un nombre completo de un tipo que implementa uno o varios contactos del servicio.

### <a name="factory"></a>Factory

El nombre de tipo de CLR del generador de host de servicio usado para crear instancias del host del servicio. Este atributo es opcional. Si no se especifica, se usa el valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>.

### <a name="debug"></a>Depuración

Indica si el servicio Windows Communication Foundation (WCF) se debe compilar con símbolos de depuración. `true` si el servicio WCF se debe compilar con símbolos de depuración; de lo contrario, `false`.

### <a name="language"></a>Lenguaje

Especifica el lenguaje usado al compilar todo el código en línea del archivo (.svc). Los valores pueden representar any. Lenguaje compatible con NET, incluidos `C#`, `VB`y `JS`, que hacen referencia a C#, Visual Basic y JScript .net, respectivamente. Este atributo es opcional.

### <a name="codebehind"></a>CodeBehind

Especifica el archivo de código fuente que implementa el servicio Web XML, cuando la clase que implementa el servicio Web XML no reside en el mismo archivo y no se ha compilado en un ensamblado y colocado en el directorio *\Bin* .

## <a name="remarks"></a>Notas

El <xref:System.ServiceModel.ServiceHost> que se usa para hospedar el servicio es un punto de extensibilidad dentro del modelo de programación de Windows Communication Foundation (WCF). Se usa un patrón del generador para crear <xref:System.ServiceModel.ServiceHost> porque es, potencialmente, un tipo polimórfico del que el entorno de hospedaje no debería crear instancias directamente.

las implementaciones predeterminadas usan <xref:System.ServiceModel.Activation.ServiceHostFactory> para crear una instancia de <xref:System.ServiceModel.ServiceHost>. Sin embargo, puede proporcionar su propio generador (uno que devuelve el host derivado) especificando el nombre de tipo de CLR de la implementación de fábrica en la Directiva `@ServiceHost`.

Para usar su propio generador de host de servicio personalizado en lugar del generador predeterminado, simplemente proporcione el nombre de tipo en la Directiva `@ServiceHost` como se indica a continuación.

```xml
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>
```

Mantenga las implementaciones del generador tan ligeras como sea posible. Si tiene mucha lógica personalizada, su código es más reutilizable si coloca esa lógica dentro de su host en lugar de dentro del generador.

Por ejemplo, para habilitar un punto de conexión habilitado para AJAX para `MyService`, especifique el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> para el valor del atributo `Factory`, en lugar del <xref:System.ServiceModel.Activation.ServiceHostFactory>predeterminado, en la Directiva `@ServiceHost`, tal como se muestra en el ejemplo siguiente:

```xml
<% @ServiceHost
Service="MyService"
Language="C#"
Debug="true"
Factory="WebScriptServiceHostFactory"
%>
```

## <a name="see-also"></a>Vea también

- [Host de servicio personalizado](../../../wcf/samples/custom-service-host.md)
