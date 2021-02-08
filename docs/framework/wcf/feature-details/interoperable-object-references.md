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
# <a name="interoperable-object-references"></a><span data-ttu-id="8e9be-103">Referencias a objetos interoperables</span><span class="sxs-lookup"><span data-stu-id="8e9be-103">Interoperable object references</span></span>

<span data-ttu-id="8e9be-104">De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> serializa los objetos por valor.</span><span class="sxs-lookup"><span data-stu-id="8e9be-104">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="8e9be-105">Puede usar la <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> propiedad para indicar al serializador del contrato de datos que debe conservar las referencias a objetos al serializar objetos.</span><span class="sxs-lookup"><span data-stu-id="8e9be-105">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="8e9be-106">XML generado</span><span class="sxs-lookup"><span data-stu-id="8e9be-106">Generated XML</span></span>  

 <span data-ttu-id="8e9be-107">A modo de ejemplo, considere el objeto siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e9be-107">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="8e9be-108">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `false` (valor predeterminado), se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e9be-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="8e9be-109">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `true`, se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e9be-109">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="8e9be-110">Sin embargo, <xref:System.Runtime.Serialization.XsdDataContractExporter> no describe `id` los `ref` atributos y en su esquema, incluso cuando la `preserveObjectReferences` propiedad está establecida en `true` .</span><span class="sxs-lookup"><span data-stu-id="8e9be-110">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="8e9be-111">Uso de IsReference</span><span class="sxs-lookup"><span data-stu-id="8e9be-111">Using IsReference</span></span>  

 <span data-ttu-id="8e9be-112">Para generar información de referencia de objeto válida de acuerdo con el esquema que lo describe, aplique el <xref:System.Runtime.Serialization.DataContractAttribute> atributo a un tipo y establezca la <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> marca en `true` .</span><span class="sxs-lookup"><span data-stu-id="8e9be-112">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="8e9be-113">En el ejemplo siguiente se modifica la clase `X` en el ejemplo anterior agregando `IsReference` :</span><span class="sxs-lookup"><span data-stu-id="8e9be-113">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="8e9be-114">El código XML generado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e9be-114">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="8e9be-115">El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8e9be-115">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="8e9be-116">Sin él, cuando se genera un tipo a partir del esquema, la salida XML para ese tipo no es necesariamente compatible con el esquema que se presuponía originalmente.</span><span class="sxs-lookup"><span data-stu-id="8e9be-116">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="8e9be-117">En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML.</span><span class="sxs-lookup"><span data-stu-id="8e9be-117">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="8e9be-118">`IsReference`Cuando se aplica a un miembro de datos, el miembro sigue siendo reconocido como *Referenciable* cuando el recorrido de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="8e9be-118">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9be-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e9be-119">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
