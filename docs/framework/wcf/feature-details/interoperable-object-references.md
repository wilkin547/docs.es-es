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
# <a name="interoperable-object-references"></a><span data-ttu-id="45f97-102">Referencias a objetos interoperables</span><span class="sxs-lookup"><span data-stu-id="45f97-102">Interoperable Object References</span></span>
<span data-ttu-id="45f97-103">De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> serializa los objetos por valor.</span><span class="sxs-lookup"><span data-stu-id="45f97-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="45f97-104">Puede usar la propiedad <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> para indicar al serializador del contrato de datos que debe conservar las referencias a objeto al serializar los objetos del tipo.</span><span class="sxs-lookup"><span data-stu-id="45f97-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="45f97-105">XML generado</span><span class="sxs-lookup"><span data-stu-id="45f97-105">Generated XML</span></span>  
 <span data-ttu-id="45f97-106">A modo de ejemplo, considere el objeto siguiente:</span><span class="sxs-lookup"><span data-stu-id="45f97-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="45f97-107">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `false` (valor predeterminado), se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="45f97-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="45f97-108">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `true`, se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="45f97-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="45f97-109">Sin embargo, <xref:System.Runtime.Serialization.XsdDataContractExporter> no describe los atributos `id` e `ref` en su esquema, incluso cuando la propiedad `preserveObjectReferences` se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="45f97-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="45f97-110">Uso de IsReference</span><span class="sxs-lookup"><span data-stu-id="45f97-110">Using IsReference</span></span>  
 <span data-ttu-id="45f97-111">Para generar información de referencia a objetos válida según el esquema que la describe, aplique el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo y establezca la marca <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="45f97-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="45f97-112">Uso de `IsReference` en la clase `X` del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="45f97-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
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
  
 <span data-ttu-id="45f97-113">El código XML generado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="45f97-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="45f97-114">El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="45f97-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="45f97-115">Si no está presente, cuando se genera un tipo desde el esquema, lo que se devuelve como XML para ese tipo no es necesariamente compatible con el esquema supuesto inicialmente.</span><span class="sxs-lookup"><span data-stu-id="45f97-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="45f97-116">En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML.</span><span class="sxs-lookup"><span data-stu-id="45f97-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="45f97-117">Cuando se aplica `IsReference` a un miembro de datos, el miembro continúa siendo reconocido como "referenciable" en los viajes de ida y vuelta (round trip).</span><span class="sxs-lookup"><span data-stu-id="45f97-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f97-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="45f97-118">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
