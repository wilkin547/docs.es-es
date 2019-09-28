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
ms.openlocfilehash: bfccdcd9b5d35418b206dfa9fefffb5ddab69c66
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592168"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="bf25e-102">GetXmlNamespace (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf25e-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="bf25e-103">Obtiene el objeto @no__t 0 que corresponde al prefijo de espacio de nombres XML especificado.</span><span class="sxs-lookup"><span data-stu-id="bf25e-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf25e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf25e-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="bf25e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="bf25e-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="bf25e-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bf25e-106">Optional.</span></span> <span data-ttu-id="bf25e-107">Cadena que identifica el prefijo del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="bf25e-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="bf25e-108">Si se proporciona, esta cadena debe ser un identificador XML válido.</span><span class="sxs-lookup"><span data-stu-id="bf25e-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="bf25e-109">Para obtener más información, vea [nombres de elementos y atributos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="bf25e-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="bf25e-110">Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bf25e-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="bf25e-111">Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.</span><span class="sxs-lookup"><span data-stu-id="bf25e-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf25e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf25e-112">Return Value</span></span>  
 <span data-ttu-id="bf25e-113">Objeto <xref:System.Xml.Linq.XNamespace> que corresponde al prefijo del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="bf25e-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf25e-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf25e-114">Remarks</span></span>  
 <span data-ttu-id="bf25e-115">El operador `GetXmlNamespace` obtiene el objeto <xref:System.Xml.Linq.XNamespace> que corresponde al prefijo de espacio de nombres XML `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="bf25e-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="bf25e-116">Puede usar prefijos de espacio de nombres XML directamente en literales XML y propiedades de eje XML.</span><span class="sxs-lookup"><span data-stu-id="bf25e-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="bf25e-117">Sin embargo, debe usar el operador `GetXmlNamespace` para convertir un prefijo de espacio de nombres en un objeto <xref:System.Xml.Linq.XNamespace> antes de poder usarlo en el código.</span><span class="sxs-lookup"><span data-stu-id="bf25e-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="bf25e-118">Puede anexar un nombre de elemento no calificado a un objeto <xref:System.Xml.Linq.XNamespace> para obtener un objeto <xref:System.Xml.Linq.XName> completo, que requieren muchos métodos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf25e-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf25e-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf25e-119">Example</span></span>  
 <span data-ttu-id="bf25e-120">En el ejemplo siguiente se importa `ns` como prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="bf25e-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="bf25e-121">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario que tiene el nombre completo `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="bf25e-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="bf25e-122">A continuación, pasa ese nodo secundario a la subrutina `ShowName`, que construye un nombre completo mediante el operador `GetXmlNamespace`.</span><span class="sxs-lookup"><span data-stu-id="bf25e-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="bf25e-123">A continuación, la subrutina `ShowName` pasa el nombre completo al método <xref:System.Xml.Linq.XNode.Ancestors%2A> para obtener el nodo primario `ns:contact`.</span><span class="sxs-lookup"><span data-stu-id="bf25e-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="bf25e-124">Cuando se llama a `TestGetXmlNamespace.RunSample()`, se muestra un cuadro de mensaje que contiene el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf25e-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="bf25e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf25e-125">See also</span></span>

- [<span data-ttu-id="bf25e-126">Imports (instrucción), espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="bf25e-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="bf25e-127">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf25e-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
