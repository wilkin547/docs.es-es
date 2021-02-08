---
description: 'Más información sobre: referencias a objetos interoperables'
title: Referencias a objetos interoperables
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 27c801fb3954c7ea3f821a6588a2229502702989
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802689"
---
# <a name="interoperable-object-references"></a>Referencias a objetos interoperables

De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> serializa los objetos por valor. Puede usar la <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> propiedad para indicar al serializador del contrato de datos que debe conservar las referencias a objetos al serializar objetos.  
  
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
  
 Sin embargo, <xref:System.Runtime.Serialization.XsdDataContractExporter> no describe `id` los `ref` atributos y en su esquema, incluso cuando la `preserveObjectReferences` propiedad está establecida en `true` .  
  
## <a name="using-isreference"></a>Uso de IsReference  

 Para generar información de referencia de objeto válida de acuerdo con el esquema que lo describe, aplique el <xref:System.Runtime.Serialization.DataContractAttribute> atributo a un tipo y establezca la <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> marca en `true` . En el ejemplo siguiente se modifica la clase `X` en el ejemplo anterior agregando `IsReference` :  
  
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
  
 El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes. Sin él, cuando se genera un tipo a partir del esquema, la salida XML para ese tipo no es necesariamente compatible con el esquema que se presuponía originalmente. En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML. `IsReference`Cuando se aplica a un miembro de datos, el miembro sigue siendo reconocido como *Referenciable* cuando el recorrido de ida y vuelta.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
