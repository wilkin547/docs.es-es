---
title: Propiedad de eje para atributos XML (Visual Basic)
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
ms.openlocfilehash: 896081c3dc7ca9e50b4dc4bd87675e957c34b649
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582163"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="6272f-102">Propiedad de eje para atributos XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6272f-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="6272f-103">Proporciona acceso al valor de un atributo para un <xref:System.Xml.Linq.XElement> objeto o al primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6272f-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6272f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6272f-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="6272f-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="6272f-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="6272f-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6272f-106">Required.</span></span> <span data-ttu-id="6272f-107">Objeto <xref:System.Xml.Linq.XElement> o colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6272f-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="6272f-108">.@</span><span class="sxs-lookup"><span data-stu-id="6272f-108">.@</span></span>  
 <span data-ttu-id="6272f-109">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6272f-109">Required.</span></span> <span data-ttu-id="6272f-110">Denota el inicio de una propiedad de eje de atributo.</span><span class="sxs-lookup"><span data-stu-id="6272f-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="6272f-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6272f-111">Optional.</span></span> <span data-ttu-id="6272f-112">Denota el principio del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6272f-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="6272f-113">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6272f-113">Required.</span></span> <span data-ttu-id="6272f-114">Nombre del atributo al que se va a tener acceso, con el formato [`prefix`:] `name`.</span><span class="sxs-lookup"><span data-stu-id="6272f-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="6272f-115">Parte</span><span class="sxs-lookup"><span data-stu-id="6272f-115">Part</span></span>|<span data-ttu-id="6272f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6272f-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="6272f-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6272f-117">Optional.</span></span> <span data-ttu-id="6272f-118">Prefijo de espacio de nombres XML para el atributo.</span><span class="sxs-lookup"><span data-stu-id="6272f-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="6272f-119">Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="6272f-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="6272f-120">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6272f-120">Required.</span></span> <span data-ttu-id="6272f-121">Nombre del atributo local.</span><span class="sxs-lookup"><span data-stu-id="6272f-121">Local attribute name.</span></span> <span data-ttu-id="6272f-122">Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6272f-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="6272f-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6272f-123">Optional.</span></span> <span data-ttu-id="6272f-124">Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6272f-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6272f-125">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6272f-125">Return Value</span></span>  
 <span data-ttu-id="6272f-126">Cadena que contiene el valor de `attribute`.</span><span class="sxs-lookup"><span data-stu-id="6272f-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="6272f-127">Si el nombre de atributo no existe, se devuelve `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6272f-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6272f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6272f-128">Remarks</span></span>  
 <span data-ttu-id="6272f-129">Puede usar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un objeto <xref:System.Xml.Linq.XElement> o desde el primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6272f-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="6272f-130">Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nuevo nombre precedido por el identificador @.</span><span class="sxs-lookup"><span data-stu-id="6272f-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="6272f-131">Cuando se hace referencia a un atributo XML mediante el identificador @, el valor del atributo se devuelve como una cadena y no es necesario especificar explícitamente la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="6272f-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="6272f-132">Las reglas de nomenclatura para los atributos XML difieren de las reglas de nomenclatura para los identificadores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6272f-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="6272f-133">Para obtener acceso a un atributo XML que tiene un nombre que no es un identificador de Visual Basic válido, incluya el nombre entre corchetes angulares (\< y >).</span><span class="sxs-lookup"><span data-stu-id="6272f-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="6272f-134">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="6272f-134">XML Namespaces</span></span>  
 <span data-ttu-id="6272f-135">El nombre de una propiedad de eje de atributo solo puede usar prefijos de espacio de nombres XML declarados globalmente mediante la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="6272f-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="6272f-136">No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="6272f-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="6272f-137">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="6272f-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6272f-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6272f-138">Example</span></span>  
 <span data-ttu-id="6272f-139">En el ejemplo siguiente se muestra cómo obtener los valores de los atributos XML denominados `type` de una colección de elementos XML que se denominan `phone`.</span><span class="sxs-lookup"><span data-stu-id="6272f-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="6272f-140">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="6272f-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="6272f-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6272f-141">Example</span></span>  
 <span data-ttu-id="6272f-142">En el ejemplo siguiente se muestra cómo crear atributos para un elemento XML mediante declaración, como parte del XML, y dinámicamente agregando un atributo a una instancia de un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6272f-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="6272f-143">El atributo `type` se crea mediante declaración y el atributo `owner` se crea dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="6272f-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="6272f-144">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="6272f-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="6272f-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6272f-145">Example</span></span>  
 <span data-ttu-id="6272f-146">En el ejemplo siguiente se usa la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type`, que no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6272f-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="6272f-147">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="6272f-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="6272f-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6272f-148">Example</span></span>  
 <span data-ttu-id="6272f-149">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="6272f-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="6272f-150">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario con el nombre completo "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="6272f-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="6272f-151">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="6272f-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="6272f-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="6272f-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="6272f-153">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="6272f-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="6272f-154">Literales XML</span><span class="sxs-lookup"><span data-stu-id="6272f-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="6272f-155">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6272f-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="6272f-156">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="6272f-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
