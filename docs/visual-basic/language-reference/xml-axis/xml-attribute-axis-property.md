---
description: 'Más información acerca de: propiedad de eje de atributo XML (Visual Basic)'
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
ms.openlocfilehash: 2085ef2151e7aef7c5642e0ba9ac2e6fa90bfd4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795175"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="f3cfc-103">Propiedad de eje para atributos XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3cfc-103">XML Attribute Axis Property (Visual Basic)</span></span>

<span data-ttu-id="f3cfc-104">Proporciona acceso al valor de un atributo para un <xref:System.Xml.Linq.XElement> objeto o al primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-104">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3cfc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3cfc-105">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="f3cfc-106">Partes</span><span class="sxs-lookup"><span data-stu-id="f3cfc-106">Parts</span></span>  

 `object`  
 <span data-ttu-id="f3cfc-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-107">Required.</span></span> <span data-ttu-id="f3cfc-108"><xref:System.Xml.Linq.XElement>Objeto o colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-108">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="f3cfc-109">.@</span><span class="sxs-lookup"><span data-stu-id="f3cfc-109">.@</span></span>  
 <span data-ttu-id="f3cfc-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-110">Required.</span></span> <span data-ttu-id="f3cfc-111">Denota el inicio de una propiedad de eje de atributo.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-111">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="f3cfc-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-112">Optional.</span></span> <span data-ttu-id="f3cfc-113">Denota el principio del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-113">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="f3cfc-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-114">Required.</span></span> <span data-ttu-id="f3cfc-115">Nombre del atributo al que se va a tener acceso, con el formato [ `prefix` :] `name` .</span><span class="sxs-lookup"><span data-stu-id="f3cfc-115">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="f3cfc-116">Parte</span><span class="sxs-lookup"><span data-stu-id="f3cfc-116">Part</span></span>|<span data-ttu-id="f3cfc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cfc-117">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="f3cfc-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-118">Optional.</span></span> <span data-ttu-id="f3cfc-119">Prefijo de espacio de nombres XML para el atributo.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-119">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="f3cfc-120">Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-120">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="f3cfc-121">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-121">Required.</span></span> <span data-ttu-id="f3cfc-122">Nombre del atributo local.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-122">Local attribute name.</span></span> <span data-ttu-id="f3cfc-123">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="f3cfc-123">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="f3cfc-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-124">Optional.</span></span> <span data-ttu-id="f3cfc-125">Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-125">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3cfc-126">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f3cfc-126">Return Value</span></span>  

 <span data-ttu-id="f3cfc-127">Cadena que contiene el valor de `attribute` .</span><span class="sxs-lookup"><span data-stu-id="f3cfc-127">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="f3cfc-128">Si el nombre de atributo no existe, `Nothing` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-128">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3cfc-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3cfc-129">Remarks</span></span>  

 <span data-ttu-id="f3cfc-130">Puede usar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un <xref:System.Xml.Linq.XElement> objeto o desde el primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-130">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="f3cfc-131">Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nuevo nombre precedido por el identificador @.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-131">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="f3cfc-132">Cuando se hace referencia a un atributo XML mediante el identificador @, el valor del atributo se devuelve como una cadena y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-132">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="f3cfc-133">Las reglas de nomenclatura para los atributos XML difieren de las reglas de nomenclatura para los identificadores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-133">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="f3cfc-134">Para obtener acceso a un atributo XML que tiene un nombre que no es un identificador de Visual Basic válido, incluya el nombre entre corchetes angulares ( \< and > ).</span><span class="sxs-lookup"><span data-stu-id="f3cfc-134">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="f3cfc-135">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="f3cfc-135">XML Namespaces</span></span>  

 <span data-ttu-id="f3cfc-136">El nombre de una propiedad de eje de atributo solo puede usar prefijos de espacio de nombres XML declarados globalmente mediante la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-136">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="f3cfc-137">No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-137">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="f3cfc-138">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="f3cfc-138">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3cfc-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3cfc-139">Example</span></span>  

 <span data-ttu-id="f3cfc-140">En el ejemplo siguiente se muestra cómo obtener los valores de los atributos XML denominados `type` de una colección de elementos XML que se denominan `phone` .</span><span class="sxs-lookup"><span data-stu-id="f3cfc-140">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="f3cfc-141">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="f3cfc-141">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="f3cfc-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3cfc-142">Example</span></span>  

 <span data-ttu-id="f3cfc-143">En el ejemplo siguiente se muestra cómo crear atributos para un elemento XML mediante declaración, como parte del XML, y dinámicamente agregando un atributo a una instancia de un <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-143">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="f3cfc-144">El `type` atributo se crea mediante declaración y el `owner` atributo se crea dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-144">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="f3cfc-145">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="f3cfc-145">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="f3cfc-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3cfc-146">Example</span></span>  

 <span data-ttu-id="f3cfc-147">En el ejemplo siguiente se usa la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type` , que no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-147">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="f3cfc-148">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="f3cfc-148">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="f3cfc-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3cfc-149">Example</span></span>  

 <span data-ttu-id="f3cfc-150">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="f3cfc-150">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="f3cfc-151">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario con el nombre completo " `ns:name` ".</span><span class="sxs-lookup"><span data-stu-id="f3cfc-151">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="f3cfc-152">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="f3cfc-152">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="f3cfc-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3cfc-153">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="f3cfc-154">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="f3cfc-154">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="f3cfc-155">Literales XML</span><span class="sxs-lookup"><span data-stu-id="f3cfc-155">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="f3cfc-156">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3cfc-156">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="f3cfc-157">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="f3cfc-157">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
