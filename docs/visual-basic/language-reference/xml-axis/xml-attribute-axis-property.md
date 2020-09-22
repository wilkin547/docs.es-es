---
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 9eddd132b2d4dd6ffbd935a0c8c57a03a3d65435
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869436"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="ac4d3-102">Propiedad de eje para atributos XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac4d3-102">XML Attribute Axis Property (Visual Basic)</span></span>

<span data-ttu-id="ac4d3-103">Proporciona acceso al valor de un atributo para un <xref:System.Xml.Linq.XElement> objeto o al primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac4d3-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="ac4d3-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ac4d3-105">Parts</span></span>  

 `object`  
 <span data-ttu-id="ac4d3-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-106">Required.</span></span> <span data-ttu-id="ac4d3-107"><xref:System.Xml.Linq.XElement>Objeto o colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="ac4d3-108">.@</span><span class="sxs-lookup"><span data-stu-id="ac4d3-108">.@</span></span>  
 <span data-ttu-id="ac4d3-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-109">Required.</span></span> <span data-ttu-id="ac4d3-110">Denota el inicio de una propiedad de eje de atributo.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="ac4d3-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-111">Optional.</span></span> <span data-ttu-id="ac4d3-112">Denota el principio del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="ac4d3-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-113">Required.</span></span> <span data-ttu-id="ac4d3-114">Nombre del atributo al que se va a tener acceso, con el formato [ `prefix` :] `name` .</span><span class="sxs-lookup"><span data-stu-id="ac4d3-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="ac4d3-115">Parte</span><span class="sxs-lookup"><span data-stu-id="ac4d3-115">Part</span></span>|<span data-ttu-id="ac4d3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac4d3-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="ac4d3-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-117">Optional.</span></span> <span data-ttu-id="ac4d3-118">Prefijo de espacio de nombres XML para el atributo.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="ac4d3-119">Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="ac4d3-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-120">Required.</span></span> <span data-ttu-id="ac4d3-121">Nombre del atributo local.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-121">Local attribute name.</span></span> <span data-ttu-id="ac4d3-122">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ac4d3-122">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="ac4d3-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-123">Optional.</span></span> <span data-ttu-id="ac4d3-124">Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac4d3-125">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac4d3-125">Return Value</span></span>  

 <span data-ttu-id="ac4d3-126">Cadena que contiene el valor de `attribute` .</span><span class="sxs-lookup"><span data-stu-id="ac4d3-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="ac4d3-127">Si el nombre de atributo no existe, `Nothing` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac4d3-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac4d3-128">Remarks</span></span>  

 <span data-ttu-id="ac4d3-129">Puede usar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un <xref:System.Xml.Linq.XElement> objeto o desde el primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ac4d3-130">Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nuevo nombre precedido por el identificador @.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="ac4d3-131">Cuando se hace referencia a un atributo XML mediante el identificador @, el valor del atributo se devuelve como una cadena y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="ac4d3-132">Las reglas de nomenclatura para los atributos XML difieren de las reglas de nomenclatura para los identificadores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="ac4d3-133">Para obtener acceso a un atributo XML que tiene un nombre que no es un identificador de Visual Basic válido, incluya el nombre entre corchetes angulares ( \< and > ).</span><span class="sxs-lookup"><span data-stu-id="ac4d3-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="ac4d3-134">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="ac4d3-134">XML Namespaces</span></span>  

 <span data-ttu-id="ac4d3-135">El nombre de una propiedad de eje de atributo solo puede usar prefijos de espacio de nombres XML declarados globalmente mediante la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="ac4d3-136">No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="ac4d3-137">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="ac4d3-137">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac4d3-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac4d3-138">Example</span></span>  

 <span data-ttu-id="ac4d3-139">En el ejemplo siguiente se muestra cómo obtener los valores de los atributos XML denominados `type` de una colección de elementos XML que se denominan `phone` .</span><span class="sxs-lookup"><span data-stu-id="ac4d3-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="ac4d3-140">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="ac4d3-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="ac4d3-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac4d3-141">Example</span></span>  

 <span data-ttu-id="ac4d3-142">En el ejemplo siguiente se muestra cómo crear atributos para un elemento XML mediante declaración, como parte del XML, y dinámicamente agregando un atributo a una instancia de un <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="ac4d3-143">El `type` atributo se crea mediante declaración y el `owner` atributo se crea dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="ac4d3-144">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="ac4d3-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="ac4d3-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac4d3-145">Example</span></span>  

 <span data-ttu-id="ac4d3-146">En el ejemplo siguiente se usa la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type` , que no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="ac4d3-147">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="ac4d3-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="ac4d3-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac4d3-148">Example</span></span>  

 <span data-ttu-id="ac4d3-149">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="ac4d3-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="ac4d3-150">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario con el nombre completo " `ns:name` ".</span><span class="sxs-lookup"><span data-stu-id="ac4d3-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="ac4d3-151">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="ac4d3-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="ac4d3-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac4d3-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="ac4d3-153">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="ac4d3-153">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="ac4d3-154">Literales XML</span><span class="sxs-lookup"><span data-stu-id="ac4d3-154">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="ac4d3-155">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac4d3-155">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="ac4d3-156">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="ac4d3-156">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
