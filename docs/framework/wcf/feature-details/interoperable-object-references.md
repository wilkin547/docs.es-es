---
title: Referencias a objetos interoperables
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: eeedd39ec14a6758395aee1f4c3b8ab26a0c2ffd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493578"
---
# <a name="interoperable-object-references"></a>Referencias a objetos interoperables
De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> serializa los objetos por valor. Puede usar la propiedad <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> para indicar al serializador del contrato de datos que debe conservar las referencias a objeto al serializar los objetos del tipo.  
  
## <a name="generated-xml"></a>XML generado  
 A modo de ejemplo, considere el objeto siguiente:  
  
```  
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
   <B ref="1" />  
</X>  
```  
  
 Sin embargo, <xref:System.Runtime.Serialization.XsdDataContractExporter> no describe los atributos `id` e `ref` en su esquema, incluso cuando la propiedad `preserveObjectReferences` se establece en `true`.  
  
## <a name="using-isreference"></a>Uso de IsReference  
 Para generar información de referencia a objetos válida según el esquema que la describe, aplique el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo y establezca la marca <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> en `true`. Uso de `IsReference` en la clase `X` del ejemplo anterior:  
  
 `[DataContract(IsReference=true)] public class X`  
  
 `{`  
  
 `SomeClass someInstance = new SomeClass();`  
  
 `[DataMember]`  
  
 `public SomeClass A = someInstance;`  
  
 `[DataMember]`  
  
 `public SomeClass B = someInstance;`  
  
 `}`  
  
 `public class SomeClass`  
  
 `{`  
  
 `}`  
  
 El código XML generado es el siguiente:  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes. Si no está presente, cuando se genera un tipo desde el esquema, lo que se devuelve como XML para ese tipo no es necesariamente compatible con el esquema supuesto inicialmente. En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML. Cuando se aplica `IsReference` a un miembro de datos, el miembro continúa siendo reconocido como "referenciable" en los viajes de ida y vuelta (round trip).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
