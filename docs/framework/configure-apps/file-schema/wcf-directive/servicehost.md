---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 3102ae8d8c28be43883eeaff6c4f829b355384a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111402"
---
# <a name="servicehost"></a>\@ServiceHost
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
  
#### <a name="service"></a>web de Office  
 El nombre del tipo de CLR del servicio hospedado. Esto debería ser un nombre completo de un tipo que implementa uno o varios contactos del servicio.  
  
#### <a name="factory"></a>Factory  
 El nombre de tipo de CLR del generador de host de servicio usado para crear instancias del host del servicio. Este atributo es opcional. Si no se especifica, se usa el valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>.  
  
#### <a name="debug"></a>Depuración  
 Indica si el servicio de Windows Communication Foundation (WCF) se debe compilar con símbolos de depuración. `true` Si el servicio de WCF se debe compilar con símbolos de depuración; en caso contrario, `false`.  
  
#### <a name="language"></a>Lenguaje  
 Especifica el lenguaje usado al compilar todo el código en línea del archivo (.svc). Los valores pueden representar cualquier lenguaje compatible con .NET, incluyendo C#, VB y JS, que hacen referencia a C#, Visual Basic .NET y JScript .NET, respectivamente. Este atributo es opcional.  
  
#### <a name="codebehind"></a>CodeBehind  
 Especifica el archivo de código fuente que implementa el servicio Web XML, cuando la clase que implementa dicho servicio no reside en el mismo archivo, y no se ha compilado en un ensamblado ni se ha colocado en el directorio \Bin.  
  
## <a name="remarks"></a>Comentarios  
 El <xref:System.ServiceModel.ServiceHost> utilizada para hospedar el servicio es un punto de extensibilidad dentro del modelo de programación de Windows Communication Foundation (WCF). Se usa un patrón del generador para crear <xref:System.ServiceModel.ServiceHost> porque es, potencialmente, un tipo polimórfico del que el entorno de hospedaje no debería crear instancias directamente.  
  
 las implementaciones predeterminadas usan <xref:System.ServiceModel.Activation.ServiceHostFactory> para crear una instancia de <xref:System.ServiceModel.ServiceHost>. Pero puede proporcionar su propio generador (uno que devuelva su host derivado) especificando el nombre del tipo CLR de la implementación de fábrica en el [ \@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva.  
  
 Para usar el generador de host de servicios personalizados propio en lugar del generador predeterminado, basta con que proporcione el nombre de tipo en el [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva como sigue:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Mantenga las implementaciones del generador tan ligeras como sea posible. Si tiene mucha lógica personalizada, su código es más reutilizable si coloca esa lógica dentro de su host en lugar de dentro del generador.  
  
 Por ejemplo, para habilitar un extremo con AJAX habilitado para `MyService`, especifique el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> para el valor de la `Factory` atributo, en lugar del predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory>, en el [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) la directiva como se muestra en el ejemplo siguiente.  
  
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

- [Host de servicio personalizado](../../../../../docs/framework/wcf/samples/custom-service-host.md)
