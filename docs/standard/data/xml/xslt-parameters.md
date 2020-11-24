---
title: Parámetros XSLT
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
ms.openlocfilehash: c203e17e327cf64690c2748c7f3a4e74b5306501
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818302"
---
# <a name="xslt-parameters"></a><span data-ttu-id="4076a-102">Parámetros XSLT</span><span class="sxs-lookup"><span data-stu-id="4076a-102">XSLT Parameters</span></span>
<span data-ttu-id="4076a-103">Los parámetros XSLT se agregan a <xref:System.Xml.Xsl.XsltArgumentList> mediante el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="4076a-103">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="4076a-104">En ese momento se asocia al objeto de parámetro un nombre completo y un identificador URI de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4076a-104">A qualified name and namespace URI are associated with the parameter object at that time.</span></span>  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="4076a-105">Para utilizar un parámetro XSLT</span><span class="sxs-lookup"><span data-stu-id="4076a-105">To use an XSLT parameter</span></span>  
  
1. <span data-ttu-id="4076a-106">Cree un objeto <xref:System.Xml.Xsl.XsltArgumentList> y agregue el parámetro utilizando el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="4076a-106">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the parameter using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span>  
  
2. <span data-ttu-id="4076a-107">Llame al parámetro desde la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="4076a-107">Call the parameter from the style sheet.</span></span>  
  
3. <span data-ttu-id="4076a-108">Pase el objeto <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="4076a-108">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="parameter-types"></a><span data-ttu-id="4076a-109">Tipos de parámetros</span><span class="sxs-lookup"><span data-stu-id="4076a-109">Parameter Types</span></span>  
 <span data-ttu-id="4076a-110">El objeto de parámetro se debería corresponder a un tipo del W3C.</span><span class="sxs-lookup"><span data-stu-id="4076a-110">The parameter object should correspond to a W3C type.</span></span> <span data-ttu-id="4076a-111">En la siguiente tabla se muestran los tipos correspondientes del W3C, las clases de Microsoft .NET Framework equivalentes (tipo) y si el tipo del W3C es un tipo XPath o un tipo XSLT.</span><span class="sxs-lookup"><span data-stu-id="4076a-111">The following table shows the corresponding W3C types, the equivalent Microsoft .NET classes (type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="4076a-112">Tipo del W3C</span><span class="sxs-lookup"><span data-stu-id="4076a-112">W3C type</span></span>|<span data-ttu-id="4076a-113">Clase equivalente de .NET (tipo)</span><span class="sxs-lookup"><span data-stu-id="4076a-113">Equivalent .NET class (type)</span></span>|<span data-ttu-id="4076a-114">Tipo XPath o XSLT</span><span class="sxs-lookup"><span data-stu-id="4076a-114">XPath or XSLT type</span></span>|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="4076a-115">XPath</span><span class="sxs-lookup"><span data-stu-id="4076a-115">XPath</span></span>|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="4076a-116">XPath</span><span class="sxs-lookup"><span data-stu-id="4076a-116">XPath</span></span>|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="4076a-117">XPath</span><span class="sxs-lookup"><span data-stu-id="4076a-117">XPath</span></span>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="4076a-118">XSLT</span><span class="sxs-lookup"><span data-stu-id="4076a-118">XSLT</span></span>|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="4076a-119">XPath</span><span class="sxs-lookup"><span data-stu-id="4076a-119">XPath</span></span>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> <span data-ttu-id="4076a-120">**XPathNavigator[]**</span><span class="sxs-lookup"><span data-stu-id="4076a-120">**XPathNavigator[]**</span></span>|<span data-ttu-id="4076a-121">XPath</span><span class="sxs-lookup"><span data-stu-id="4076a-121">XPath</span></span>|  
  
 <span data-ttu-id="4076a-122">\*Es equivalente a un conjunto de nodos que contiene un solo nodo.</span><span class="sxs-lookup"><span data-stu-id="4076a-122">\*This is equivalent to a node set that contains a single node.</span></span>  
  
 <span data-ttu-id="4076a-123">Si el objeto de parámetro no pertenece a una de las clases anteriores, se convierte de acuerdo con las siguientes reglas.</span><span class="sxs-lookup"><span data-stu-id="4076a-123">If the parameter object is not one of the above classes, it is converted according to the following rules.</span></span> <span data-ttu-id="4076a-124">Los tipos de Common Language Runtime (CLR) numéricos se convierten en <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="4076a-124">Common language runtime (CLR) numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="4076a-125">El tipo <xref:System.DateTime> se convierte en <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="4076a-125">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="4076a-126">Los tipos <xref:System.Xml.XPath.IXPathNavigable> se convierten en <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="4076a-126"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="4076a-127">**XPathNavigator[]** se convierte en <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="4076a-127">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="4076a-128">El resto de los tipos inician un error.</span><span class="sxs-lookup"><span data-stu-id="4076a-128">All other types throw an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4076a-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4076a-129">Example</span></span>  
 <span data-ttu-id="4076a-130">En el ejemplo siguiente se utiliza el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> para crear un parámetro que almacena la fecha de descuento calculada.</span><span class="sxs-lookup"><span data-stu-id="4076a-130">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold calculated discount date.</span></span> <span data-ttu-id="4076a-131">Para calcular la fecha de descuento se deben sumar 20 días a partir de la fecha del pedido.</span><span class="sxs-lookup"><span data-stu-id="4076a-131">The discount date is calculated to be 20 days from the order date.</span></span>  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="4076a-132">Entrada</span><span class="sxs-lookup"><span data-stu-id="4076a-132">Input</span></span>  
  
##### <a name="orderxml"></a><span data-ttu-id="4076a-133">order.xml</span><span class="sxs-lookup"><span data-stu-id="4076a-133">order.xml</span></span>  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a><span data-ttu-id="4076a-134">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="4076a-134">discount.xsl</span></span>  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="4076a-135">Salida</span><span class="sxs-lookup"><span data-stu-id="4076a-135">Output</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4076a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4076a-136">See also</span></span>

- [<span data-ttu-id="4076a-137">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="4076a-137">XSLT Transformations</span></span>](xslt-transformations.md)
