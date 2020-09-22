---
title: Operador GetXmlNamespace
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 660474c1193076755889fd885c1b78bec78f0a2c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873469"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="0eb30-102">GetXmlNamespace (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb30-102">GetXmlNamespace Operator (Visual Basic)</span></span>

<span data-ttu-id="0eb30-103">Obtiene el <xref:System.Xml.Linq.XNamespace> objeto que corresponde al prefijo de espacio de nombres XML especificado.</span><span class="sxs-lookup"><span data-stu-id="0eb30-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eb30-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="0eb30-105">Partes</span><span class="sxs-lookup"><span data-stu-id="0eb30-105">Parts</span></span>  

 `xmlNamespacePrefix`  
 <span data-ttu-id="0eb30-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0eb30-106">Optional.</span></span> <span data-ttu-id="0eb30-107">Cadena que identifica el prefijo del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="0eb30-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="0eb30-108">Si se proporciona, esta cadena debe ser un identificador XML válido.</span><span class="sxs-lookup"><span data-stu-id="0eb30-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="0eb30-109">Para obtener más información, vea [nombres de elementos y atributos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="0eb30-109">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="0eb30-110">Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0eb30-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="0eb30-111">Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.</span><span class="sxs-lookup"><span data-stu-id="0eb30-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0eb30-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0eb30-112">Return Value</span></span>  

 <span data-ttu-id="0eb30-113"><xref:System.Xml.Linq.XNamespace>Objeto que corresponde al prefijo del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="0eb30-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0eb30-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0eb30-114">Remarks</span></span>  

 <span data-ttu-id="0eb30-115">El `GetXmlNamespace` operador obtiene el <xref:System.Xml.Linq.XNamespace> objeto que corresponde al prefijo del espacio de nombres XML `xmlNamespacePrefix` .</span><span class="sxs-lookup"><span data-stu-id="0eb30-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="0eb30-116">Puede usar prefijos de espacio de nombres XML directamente en literales XML y propiedades de eje XML.</span><span class="sxs-lookup"><span data-stu-id="0eb30-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="0eb30-117">Sin embargo, debe usar el `GetXmlNamespace` operador para convertir un prefijo de espacio de nombres en un <xref:System.Xml.Linq.XNamespace> objeto antes de poder usarlo en el código.</span><span class="sxs-lookup"><span data-stu-id="0eb30-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="0eb30-118">Puede anexar un nombre de elemento no calificado a un <xref:System.Xml.Linq.XNamespace> objeto para obtener un <xref:System.Xml.Linq.XName> objeto completo, que requieren muchos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] métodos.</span><span class="sxs-lookup"><span data-stu-id="0eb30-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eb30-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0eb30-119">Example</span></span>  

 <span data-ttu-id="0eb30-120">En el ejemplo siguiente se importa `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="0eb30-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="0eb30-121">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario que tiene el nombre completo `ns:phone` .</span><span class="sxs-lookup"><span data-stu-id="0eb30-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="0eb30-122">A continuación, pasa ese nodo secundario a la `ShowName` subrutina, que construye un nombre completo mediante el `GetXmlNamespace` operador.</span><span class="sxs-lookup"><span data-stu-id="0eb30-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="0eb30-123">`ShowName`A continuación, la subrutina pasa el nombre completo al <xref:System.Xml.Linq.XNode.Ancestors%2A> método para obtener el `ns:contact` nodo primario.</span><span class="sxs-lookup"><span data-stu-id="0eb30-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="0eb30-124">Cuando se llama a `TestGetXmlNamespace.RunSample()` , se muestra un cuadro de mensaje que contiene el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="0eb30-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="0eb30-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0eb30-125">See also</span></span>

- [<span data-ttu-id="0eb30-126">Imports (Instrucción, Espacio de nombres XML)</span><span class="sxs-lookup"><span data-stu-id="0eb30-126">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="0eb30-127">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0eb30-127">Accessing XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/accessing-xml.md)
