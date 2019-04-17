---
title: Referencias a objetos interoperables
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610644"
---
# <a name="interoperable-object-references"></a>Referencias a objetos interoperables
De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> serializa los objetos por valor. Puede usar el <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> propiedad para indicar el serializador de contratos de datos para conservar las referencias a objetos al serializar objetos.  
  
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
  
 Sin embargo, <xref:System.Runtime.Serialization.XsdDataContractExporter> no describe la `id` y `ref` atributos en su esquema, incluso cuando el `preserveObjectReferences` propiedad está establecida en `true`.  
  
## <a name="using-isreference"></a>Uso de IsReference  
 Para generar información de referencia de objeto es válido según el esquema que lo describe, aplique el <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo de atributo y establecer el <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> marca `true`. El ejemplo siguiente modifica la clase `X` en el ejemplo anterior mediante la adición de `IsReference`:  
  
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
  
 El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes. Sin él, cuando se genera un tipo de esquema, la salida XML para que el tipo no es necesariamente compatible con el esquema supuesto inicialmente. En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML. Con `IsReference` aplicado a un miembro de datos, el miembro continúa siendo reconocido como *referenceable* cuando ida y vuelta.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
