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
# <a name="interoperable-object-references"></a><span data-ttu-id="e8636-102">Referencias a objetos interoperables</span><span class="sxs-lookup"><span data-stu-id="e8636-102">Interoperable object references</span></span>
<span data-ttu-id="e8636-103">De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> serializa los objetos por valor.</span><span class="sxs-lookup"><span data-stu-id="e8636-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="e8636-104">Puede usar el <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> propiedad para indicar el serializador de contratos de datos para conservar las referencias a objetos al serializar objetos.</span><span class="sxs-lookup"><span data-stu-id="e8636-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="e8636-105">XML generado</span><span class="sxs-lookup"><span data-stu-id="e8636-105">Generated XML</span></span>  
 <span data-ttu-id="e8636-106">A modo de ejemplo, considere el objeto siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8636-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="e8636-107">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `false` (valor predeterminado), se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8636-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="e8636-108">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> establecido en `true`, se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8636-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="e8636-109">Sin embargo, <xref:System.Runtime.Serialization.XsdDataContractExporter> no describe la `id` y `ref` atributos en su esquema, incluso cuando el `preserveObjectReferences` propiedad está establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="e8636-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="e8636-110">Uso de IsReference</span><span class="sxs-lookup"><span data-stu-id="e8636-110">Using IsReference</span></span>  
 <span data-ttu-id="e8636-111">Para generar información de referencia de objeto es válido según el esquema que lo describe, aplique el <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo de atributo y establecer el <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> marca `true`.</span><span class="sxs-lookup"><span data-stu-id="e8636-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="e8636-112">El ejemplo siguiente modifica la clase `X` en el ejemplo anterior mediante la adición de `IsReference`:</span><span class="sxs-lookup"><span data-stu-id="e8636-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="e8636-113">El código XML generado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8636-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A> 
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="e8636-114">El uso de `IsReference` garantiza la compatibilidad en los viajes de ida y vuelta (round trip) de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e8636-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="e8636-115">Sin él, cuando se genera un tipo de esquema, la salida XML para que el tipo no es necesariamente compatible con el esquema supuesto inicialmente.</span><span class="sxs-lookup"><span data-stu-id="e8636-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="e8636-116">En otras palabras, aunque se serializasen los atributos `id` e `ref`, el esquema original podría haber excluido estos atributos (o todos los atributos) en el código XML.</span><span class="sxs-lookup"><span data-stu-id="e8636-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="e8636-117">Con `IsReference` aplicado a un miembro de datos, el miembro continúa siendo reconocido como *referenceable* cuando ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="e8636-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8636-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8636-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
