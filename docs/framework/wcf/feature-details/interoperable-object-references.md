---
title: Referencias de objetos interoperables
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 0927f217a1666f8f27ca9c3e68f80a96b9c0f2b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184704"
---
# <a name="interoperable-object-references"></a>Referencias de objetos interoperables
De forma <xref:System.Runtime.Serialization.DataContractSerializer> predeterminada, serializa los objetos por valor. Puede utilizar <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> la propiedad para indicar al serializador de contratos de datos que conserve las referencias a objetos al serializar objetos.  
  
## <a name="generated-xml"></a>XML generado  
 A modo de ejemplo, considere el objeto siguiente:  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `false` (valor predeterminado), se genera el código XML siguiente:  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `true`, se genera el código XML siguiente:  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 Sin <xref:System.Runtime.Serialization.XsdDataContractExporter> embargo, no `id` `ref` describe los atributos y `preserveObjectReferences` en su `true`esquema, incluso cuando la propiedad está establecida en .  
  
## <a name="using-isreference"></a>Uso de IsReference  
 Para generar información de referencia de objeto que sea válida <xref:System.Runtime.Serialization.DataContractAttribute> según el esquema que <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> la `true`describe, aplique el atributo a un tipo y establezca la marca en . En el ejemplo `X` siguiente se modifica `IsReference`la clase del ejemplo anterior agregando:  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 El código XML generado es el siguiente:  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes. Sin él, cuando se genera un tipo a partir de un esquema, la salida XML para ese tipo no es necesariamente compatible con el esquema asumido originalmente. En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML. Con `IsReference` aplicado a un miembro de datos, el miembro sigue siendo reconocido como *referenciable* cuando se viaja de ida y vuelta.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
