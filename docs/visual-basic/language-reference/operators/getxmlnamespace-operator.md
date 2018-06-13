---
title: GetXmlNamespace (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: e21cf160d10f308990894d1a85c4f5d05b90f68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603488"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="90d31-102">GetXmlNamespace (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90d31-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="90d31-103">Obtiene el <xref:System.Xml.Linq.XNamespace> objeto que se corresponde con el prefijo de espacio de nombres XML especificado.</span><span class="sxs-lookup"><span data-stu-id="90d31-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90d31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90d31-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="90d31-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="90d31-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="90d31-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="90d31-106">Optional.</span></span> <span data-ttu-id="90d31-107">La cadena que identifica el prefijo del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="90d31-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="90d31-108">Si se proporciona, esta cadena debe ser un identificador XML válido.</span><span class="sxs-lookup"><span data-stu-id="90d31-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="90d31-109">Para obtener más información, consulte [nombres de declarar elementos y atributos XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="90d31-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="90d31-110">Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="90d31-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="90d31-111">Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.</span><span class="sxs-lookup"><span data-stu-id="90d31-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90d31-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="90d31-112">Return Value</span></span>  
 <span data-ttu-id="90d31-113">La <xref:System.Xml.Linq.XNamespace> objeto que se corresponde con el prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="90d31-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90d31-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90d31-114">Remarks</span></span>  
 <span data-ttu-id="90d31-115">El `GetXmlNamespace` operador obtiene la <xref:System.Xml.Linq.XNamespace> objeto que se corresponde con el prefijo de espacio de nombres XML `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="90d31-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="90d31-116">Puede usar los prefijos de espacio de nombres XML directamente en literales XML y propiedades de eje XML.</span><span class="sxs-lookup"><span data-stu-id="90d31-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="90d31-117">Sin embargo, debe utilizar el `GetXmlNamespace` operador para convertir un prefijo de espacio de nombres para un <xref:System.Xml.Linq.XNamespace> objeto antes de que se puede usar en el código.</span><span class="sxs-lookup"><span data-stu-id="90d31-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="90d31-118">Puede anexar un nombre de elemento sin calificar a un <xref:System.Xml.Linq.XNamespace> objeto que se va a obtener un completo <xref:System.Xml.Linq.XName> objeto qué varios [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] métodos requieren.</span><span class="sxs-lookup"><span data-stu-id="90d31-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90d31-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90d31-119">Example</span></span>  
 <span data-ttu-id="90d31-120">El ejemplo siguiente importa `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="90d31-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="90d31-121">A continuación, utiliza el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario que tiene el nombre completo `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="90d31-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="90d31-122">A continuación, pasa ese nodo secundario a la `ShowName` subrutina, que crea un nombre completo mediante el `GetXmlNamespace` operador.</span><span class="sxs-lookup"><span data-stu-id="90d31-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="90d31-123">El `ShowName` subrutina, a continuación, pasa el nombre completo para la <xref:System.Xml.Linq.XNode.Ancestors%2A> método para obtener el elemento primario `ns:contact` nodo.</span><span class="sxs-lookup"><span data-stu-id="90d31-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 <span data-ttu-id="90d31-124">Cuando se llama a `TestGetXmlNamespace.RunSample()`, muestra un cuadro de mensaje que contiene el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="90d31-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="90d31-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="90d31-125">See Also</span></span>  
 [<span data-ttu-id="90d31-126">Imports (instrucción), espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="90d31-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="90d31-127">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90d31-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
