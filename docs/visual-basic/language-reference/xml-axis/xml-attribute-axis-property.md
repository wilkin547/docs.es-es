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
ms.openlocfilehash: 9107b946394ab70980e4865364fc1ba9683e2025
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539968"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="79b18-102">Propiedad de eje para atributos XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79b18-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="79b18-103">Proporciona acceso al valor de un atributo para un <xref:System.Xml.Linq.XElement> objeto o en el primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="79b18-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79b18-104">Syntax</span></span>  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="79b18-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="79b18-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="79b18-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="79b18-106">Required.</span></span> <span data-ttu-id="79b18-107">Un <xref:System.Xml.Linq.XElement> objeto o una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="79b18-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="79b18-108">.@</span><span class="sxs-lookup"><span data-stu-id="79b18-108">.@</span></span>  
 <span data-ttu-id="79b18-109">Requerido.</span><span class="sxs-lookup"><span data-stu-id="79b18-109">Required.</span></span> <span data-ttu-id="79b18-110">Denota el inicio de una propiedad de eje de atributo.</span><span class="sxs-lookup"><span data-stu-id="79b18-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="79b18-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79b18-111">Optional.</span></span> <span data-ttu-id="79b18-112">Indica el principio del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="79b18-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="79b18-113">Requerido.</span><span class="sxs-lookup"><span data-stu-id="79b18-113">Required.</span></span> <span data-ttu-id="79b18-114">Nombre del atributo para tener acceso a la forma [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="79b18-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="79b18-115">Parte</span><span class="sxs-lookup"><span data-stu-id="79b18-115">Part</span></span>|<span data-ttu-id="79b18-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="79b18-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="79b18-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79b18-117">Optional.</span></span> <span data-ttu-id="79b18-118">Prefijo de espacio de nombres XML para el atributo.</span><span class="sxs-lookup"><span data-stu-id="79b18-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="79b18-119">Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="79b18-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="79b18-120">Requerido.</span><span class="sxs-lookup"><span data-stu-id="79b18-120">Required.</span></span> <span data-ttu-id="79b18-121">Nombre del atributo local.</span><span class="sxs-lookup"><span data-stu-id="79b18-121">Local attribute name.</span></span> <span data-ttu-id="79b18-122">Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="79b18-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="79b18-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79b18-123">Optional.</span></span> <span data-ttu-id="79b18-124">Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="79b18-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79b18-125">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79b18-125">Return Value</span></span>  
 <span data-ttu-id="79b18-126">Una cadena que contiene el valor de `attribute`.</span><span class="sxs-lookup"><span data-stu-id="79b18-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="79b18-127">Si no existe el nombre del atributo, `Nothing` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="79b18-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79b18-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79b18-128">Remarks</span></span>  
 <span data-ttu-id="79b18-129">Puede usar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un <xref:System.Xml.Linq.XElement> objeto o desde el primer elemento en una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="79b18-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="79b18-130">Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nuevo nombre precedido por el identificador @.</span><span class="sxs-lookup"><span data-stu-id="79b18-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="79b18-131">Cuando hace referencia a un atributo XML mediante el identificador @, se devuelve el valor del atributo como una cadena y no es necesario especificar explícitamente el <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="79b18-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="79b18-132">Las reglas de nomenclatura para los atributos XML difieren de las reglas de nomenclatura para los identificadores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="79b18-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="79b18-133">Para obtener acceso a un atributo XML que tiene un nombre que no es un identificador válido de Visual Basic, enciérrela entre corchetes angulares (\< y >).</span><span class="sxs-lookup"><span data-stu-id="79b18-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="79b18-134">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="79b18-134">XML Namespaces</span></span>  
 <span data-ttu-id="79b18-135">El nombre de una propiedad de eje de atributo puede usar únicamente prefijos espacios de nombres XML declarados globalmente mediante la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="79b18-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="79b18-136">No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="79b18-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="79b18-137">Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="79b18-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79b18-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79b18-138">Example</span></span>  
 <span data-ttu-id="79b18-139">El ejemplo siguiente muestra cómo obtener los valores de los atributos XML denominados `type` de una colección de elementos XML que se denominan `phone`.</span><span class="sxs-lookup"><span data-stu-id="79b18-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 <span data-ttu-id="79b18-140">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="79b18-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="79b18-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79b18-141">Example</span></span>  
 <span data-ttu-id="79b18-142">El ejemplo siguiente muestra cómo crear atributos para un elemento XML tanto de forma declarativa, como parte del código XML y dinámicamente mediante la adición de un atributo a una instancia de un <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="79b18-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="79b18-143">El `type` atributo se crea mediante declaración y la `owner` atributo se crea dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="79b18-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 <span data-ttu-id="79b18-144">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="79b18-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="79b18-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79b18-145">Example</span></span>  
 <span data-ttu-id="79b18-146">En el ejemplo siguiente se usa la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type`, que no es un identificador válido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="79b18-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 <span data-ttu-id="79b18-147">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="79b18-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="79b18-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79b18-148">Example</span></span>  
 <span data-ttu-id="79b18-149">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="79b18-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="79b18-150">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="79b18-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 <span data-ttu-id="79b18-151">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="79b18-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="79b18-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="79b18-152">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="79b18-153">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="79b18-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)  
 [<span data-ttu-id="79b18-154">Literales XML</span><span class="sxs-lookup"><span data-stu-id="79b18-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="79b18-155">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79b18-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="79b18-156">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="79b18-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
