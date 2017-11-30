---
title: Resultados de XslTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 92bf2d7184ca2eb8b17c1d83130c66d1f33f0483
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="outputs-from-an-xsltransform"></a><span data-ttu-id="95a18-102">Resultados de XslTransform</span><span class="sxs-lookup"><span data-stu-id="95a18-102">Outputs from an XslTransform</span></span>
<span data-ttu-id="95a18-103">Como las hojas de estilos pueden determinar el formato del resultado utilizando una instrucción `<xsl:output>` con el atributo `method`, en la tabla siguiente se describe cuál es el formato del resultado cuando se utiliza el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> para escribir el resultado, y el formato del resultado se declara como <xref:System.IO.Stream> o <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="95a18-103">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95a18-104">La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95a18-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="95a18-105">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="95a18-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="95a18-106">Vea [mediante la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="95a18-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="95a18-107">Como las hojas de estilos pueden determinar el formato del resultado utilizando una instrucción `<xsl:output>` con el atributo `method`, en la tabla siguiente se describe cuál es el formato del resultado cuando se utiliza el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> para escribir el resultado, y el formato del resultado se declara como <xref:System.IO.Stream> o <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="95a18-107">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="95a18-108">En la tabla siguiente se describe lo que sucede cuando un tipo de resultado se declara mediante el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> junto con una instrucción `<xsl:output>`:</span><span class="sxs-lookup"><span data-stu-id="95a18-108">The following table describes what happens when an output type is declared by the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method in conjunction with the use of an `<xsl:output>` statement:</span></span>  
  
|<span data-ttu-id="95a18-109">\<método xsl: output = > atributo</span><span class="sxs-lookup"><span data-stu-id="95a18-109">\<xsl:output method = > attribute</span></span>|<span data-ttu-id="95a18-110">Formato del resultado</span><span class="sxs-lookup"><span data-stu-id="95a18-110">Result format</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="95a18-111">method="xml"</span><span class="sxs-lookup"><span data-stu-id="95a18-111">method="xml"</span></span>|<span data-ttu-id="95a18-112">XML</span><span class="sxs-lookup"><span data-stu-id="95a18-112">XML</span></span>|  
|<span data-ttu-id="95a18-113">method="html"</span><span class="sxs-lookup"><span data-stu-id="95a18-113">method="html"</span></span>|<span data-ttu-id="95a18-114">HTML</span><span class="sxs-lookup"><span data-stu-id="95a18-114">HTML</span></span>|  
|<span data-ttu-id="95a18-115">method="text"</span><span class="sxs-lookup"><span data-stu-id="95a18-115">method="text"</span></span>|<span data-ttu-id="95a18-116">Texto</span><span class="sxs-lookup"><span data-stu-id="95a18-116">Text</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="95a18-117">Nota: la instrucción `<xsl:output>` se ignora cuando el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="95a18-117">Note: The `<xsl:output>` statement is ignored when the output of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="95a18-118">Los siguientes atributos son compatibles cuando el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.IO.Stream> o <xref:System.IO.TextWriter>:</span><span class="sxs-lookup"><span data-stu-id="95a18-118">The following attributes are supported when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>:</span></span>  
  
-   <span data-ttu-id="95a18-119">encoding*</span><span class="sxs-lookup"><span data-stu-id="95a18-119">encoding*</span></span>  
  
-   <span data-ttu-id="95a18-120">omit-xml-declaration</span><span class="sxs-lookup"><span data-stu-id="95a18-120">omit-xml-declaration</span></span>  
  
-   <span data-ttu-id="95a18-121">independiente</span><span class="sxs-lookup"><span data-stu-id="95a18-121">standalone</span></span>  
  
-   <span data-ttu-id="95a18-122">doctype-public</span><span class="sxs-lookup"><span data-stu-id="95a18-122">doctype-public</span></span>  
  
-   <span data-ttu-id="95a18-123">doctype-system</span><span class="sxs-lookup"><span data-stu-id="95a18-123">doctype-system</span></span>  
  
-   <span data-ttu-id="95a18-124">cdata-section-elements</span><span class="sxs-lookup"><span data-stu-id="95a18-124">cdata-section-elements</span></span>  
  
-   <span data-ttu-id="95a18-125">indent</span><span class="sxs-lookup"><span data-stu-id="95a18-125">indent</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95a18-126">*el atributo encoding se omite cuando el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> envía su resultado a <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="95a18-126">*the encoding attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is sending its output to a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="95a18-127">Se usa en su lugar la propiedad encoding de <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="95a18-127">The encoding property on the <xref:System.IO.TextWriter> is used instead.</span></span>  
  
 <span data-ttu-id="95a18-128">El atributo siguiente se omite si el resultado del método <xref:System.Xml.Xsl.XslTransform.Transform%2A> es <xref:System.IO.Stream>:</span><span class="sxs-lookup"><span data-stu-id="95a18-128">The following attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream>:</span></span>  
  
-   <span data-ttu-id="95a18-129">versión: la versión es siempre 1.0.</span><span class="sxs-lookup"><span data-stu-id="95a18-129">version: the version is always 1.0</span></span>  
  
-   <span data-ttu-id="95a18-130">tipo de medio: el tipo de medio</span><span class="sxs-lookup"><span data-stu-id="95a18-130">media-type: the media-type</span></span>  
  
## <a name="escaping-special-characters"></a><span data-ttu-id="95a18-131">Caracteres de escape especiales</span><span class="sxs-lookup"><span data-stu-id="95a18-131">Escaping Special Characters</span></span>  
 <span data-ttu-id="95a18-132">La etiqueta `<xsl:text disable-output-escaping>` se utiliza para indicar si los caracteres especiales tienen que ser caracteres de escape en formato XML (por ejemplo, mediante `<&lt>` en lugar del símbolo `"<"`) o izquierda en el estado actual.</span><span class="sxs-lookup"><span data-stu-id="95a18-132">The `<xsl:text disable-output-escaping>` tag is used to indicate whether or not special characters need to be escaped into an XML form (for example, using `<&lt>` in place of the `"<"` symbol) or left in the present condition.</span></span> <span data-ttu-id="95a18-133">El atributo `disable-output-escaping` se omite cuando se transforma en un objeto <xref:System.Xml.XmlReader> o<xref:System.Xml.XmlWriter> y no afecta a caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="95a18-133">The `disable-output-escaping` attribute is ignored when transforming to an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter> object and has no effect on special characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95a18-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="95a18-134">See Also</span></span>  
 [<span data-ttu-id="95a18-135">Clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="95a18-135">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
