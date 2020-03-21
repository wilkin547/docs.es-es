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
# <a name="interoperable-object-references"></a><span data-ttu-id="07335-102">Referencias de objetos interoperables</span><span class="sxs-lookup"><span data-stu-id="07335-102">Interoperable object references</span></span>
<span data-ttu-id="07335-103">De forma <xref:System.Runtime.Serialization.DataContractSerializer> predeterminada, serializa los objetos por valor.</span><span class="sxs-lookup"><span data-stu-id="07335-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="07335-104">Puede utilizar <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> la propiedad para indicar al serializador de contratos de datos que conserve las referencias a objetos al serializar objetos.</span><span class="sxs-lookup"><span data-stu-id="07335-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="07335-105">XML generado</span><span class="sxs-lookup"><span data-stu-id="07335-105">Generated XML</span></span>  
 <span data-ttu-id="07335-106">A modo de ejemplo, considere el objeto siguiente:</span><span class="sxs-lookup"><span data-stu-id="07335-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="07335-107">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `false` (valor predeterminado), se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="07335-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="07335-108">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `true`, se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="07335-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="07335-109">Sin <xref:System.Runtime.Serialization.XsdDataContractExporter> embargo, no `id` `ref` describe los atributos y `preserveObjectReferences` en su `true`esquema, incluso cuando la propiedad está establecida en .</span><span class="sxs-lookup"><span data-stu-id="07335-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="07335-110">Uso de IsReference</span><span class="sxs-lookup"><span data-stu-id="07335-110">Using IsReference</span></span>  
 <span data-ttu-id="07335-111">Para generar información de referencia de objeto que sea válida <xref:System.Runtime.Serialization.DataContractAttribute> según el esquema que <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> la `true`describe, aplique el atributo a un tipo y establezca la marca en .</span><span class="sxs-lookup"><span data-stu-id="07335-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="07335-112">En el ejemplo `X` siguiente se modifica `IsReference`la clase del ejemplo anterior agregando:</span><span class="sxs-lookup"><span data-stu-id="07335-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="07335-113">El código XML generado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="07335-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="07335-114">El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="07335-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="07335-115">Sin él, cuando se genera un tipo a partir de un esquema, la salida XML para ese tipo no es necesariamente compatible con el esquema asumido originalmente.</span><span class="sxs-lookup"><span data-stu-id="07335-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="07335-116">En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML.</span><span class="sxs-lookup"><span data-stu-id="07335-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="07335-117">Con `IsReference` aplicado a un miembro de datos, el miembro sigue siendo reconocido como *referenciable* cuando se viaja de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="07335-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07335-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07335-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
