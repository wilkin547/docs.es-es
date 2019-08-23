---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: a56fb1bb9395425222347914fe3f4c17f1a451b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920336"
---
# <a name="servicehost"></a>\@Apertura
Asocia el generador usado para crear el host del servicio con el servicio que se va a hospedar y otros aspectos de programación necesarios para tener acceso o compilar el código de hospedaje proporcionado en el archivo .svc.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a>Atributos  
  
#### <a name="service"></a>Servicio  
 El nombre del tipo de CLR del servicio hospedado. Esto debería ser un nombre completo de un tipo que implementa uno o varios contactos del servicio.  
  
#### <a name="factory"></a>Factory  
 El nombre de tipo de CLR del generador de host de servicio usado para crear instancias del host del servicio. Este atributo es opcional. Si no se especifica, se usa el valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>.  
  
#### <a name="debug"></a>Depuración  
 Indica si el servicio Windows Communication Foundation (WCF) se debe compilar con símbolos de depuración. `true`Si el servicio WCF se debe compilar con símbolos de depuración; en caso `false`contrario,.  
  
#### <a name="language"></a>Idioma  
 Especifica el lenguaje usado al compilar todo el código en línea del archivo (.svc). Los valores pueden representar cualquier lenguaje compatible con .NET, incluyendo C#, VB y JS, que hacen referencia a C#, Visual Basic .NET y JScript .NET, respectivamente. Este atributo es opcional.  
  
#### <a name="codebehind"></a>CodeBehind  
 Especifica el archivo de código fuente que implementa el servicio Web XML, cuando la clase que implementa dicho servicio no reside en el mismo archivo, y no se ha compilado en un ensamblado ni se ha colocado en el directorio \Bin.  
  
## <a name="remarks"></a>Comentarios  
 El <xref:System.ServiceModel.ServiceHost> que se usa para hospedar el servicio es un punto de extensibilidad dentro del modelo de programación de Windows Communication Foundation (WCF). Se usa un patrón del generador para crear <xref:System.ServiceModel.ServiceHost> porque es, potencialmente, un tipo polimórfico del que el entorno de hospedaje no debería crear instancias directamente.  
  
 las implementaciones predeterminadas usan <xref:System.ServiceModel.Activation.ServiceHostFactory> para crear una instancia de <xref:System.ServiceModel.ServiceHost>. Sin embargo, puede proporcionar su propio generador (uno que devuelve el host derivado) especificando el nombre de tipo de CLR de la implementación de [ \@](servicehost.md) fábrica en la Directiva ServiceHost.  
  
 Para usar su propio generador de host de servicio personalizado en lugar del generador predeterminado, simplemente proporcione el nombre de tipo [@ServiceHost](servicehost.md) en la Directiva de la siguiente manera:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Mantenga las implementaciones del generador tan ligeras como sea posible. Si tiene mucha lógica personalizada, su código es más reutilizable si coloca esa lógica dentro de su host en lugar de dentro del generador.  
  
 Por ejemplo, para habilitar un extremo habilitado para Ajax `MyService`para, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> especifique `Factory` para el valor del atributo, en lugar del valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory>, en la [@ServiceHost](servicehost.md) Directiva, tal como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a>Vea también

- [Host de servicio personalizado](../../../wcf/samples/custom-service-host.md)
