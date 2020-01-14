---
title: Uso de la clase XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 6fc29b523e59590138cb7ca4db1b0da1bfee99c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937944"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="54b72-102">Uso de la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="54b72-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="54b72-103">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT de Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="54b72-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="54b72-104">Esta clase se utiliza para compilar hojas de estilos y ejecutar transformaciones XSLT.</span><span class="sxs-lookup"><span data-stu-id="54b72-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54b72-105">Aunque el rendimiento total de la clase <xref:System.Xml.Xsl.XslCompiledTransform> es mejor que la clase <xref:System.Xml.Xsl.XslTransform>, el método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslCompiledTransform> podría ser más lento que el método <xref:System.Xml.Xsl.XslTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslTransform> cuando se le llama por primera vez para una transformación.</span><span class="sxs-lookup"><span data-stu-id="54b72-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="54b72-106">Esto se debe a que el archivo XSLT debe compilarse antes de cargarse.</span><span class="sxs-lookup"><span data-stu-id="54b72-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="54b72-107">Para obtener más información, vea el siguiente blog: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform) (¿XslCompiledTransform es más lento que XslTransform?).</span><span class="sxs-lookup"><span data-stu-id="54b72-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54b72-108">Esta sección</span><span class="sxs-lookup"><span data-stu-id="54b72-108">In This Section</span></span>  
 [<span data-ttu-id="54b72-109">Entradas en la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="54b72-109">Inputs to the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="54b72-110">Describe las opciones de entrada XSLT disponibles.</span><span class="sxs-lookup"><span data-stu-id="54b72-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="54b72-111">Opciones de salida en la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="54b72-111">Output Options on the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="54b72-112">Describe las opciones de salida XSLT disponibles.</span><span class="sxs-lookup"><span data-stu-id="54b72-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="54b72-113">Resolución de recursos externos durante el procesamiento XSLT</span><span class="sxs-lookup"><span data-stu-id="54b72-113">Resolving External Resources During XSLT Processing</span></span>](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="54b72-114">Describe el uso de la clase <xref:System.Xml.XmlResolver> para resolver recursos externos.</span><span class="sxs-lookup"><span data-stu-id="54b72-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="54b72-115">Extensión de hojas de estilos SXLT</span><span class="sxs-lookup"><span data-stu-id="54b72-115">Extending XSLT Style Sheets</span></span>](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 <span data-ttu-id="54b72-116">Describe cómo se admiten las extensiones XSLT.</span><span class="sxs-lookup"><span data-stu-id="54b72-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="54b72-117">Errores XSLT recuperables</span><span class="sxs-lookup"><span data-stu-id="54b72-117">Recoverable XSLT Errors</span></span>](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|<span data-ttu-id="54b72-118">Enumera cada uno de los comportamientos discrecionales que permite la recomendación XSLT 1.0 del W3C y describe cómo la clase <xref:System.Xml.Xsl.XslCompiledTransform> controla estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="54b72-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="54b72-119">Transformación de un fragmento de nodo</span><span class="sxs-lookup"><span data-stu-id="54b72-119">How to: Transform a Node Fragment</span></span>](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|<span data-ttu-id="54b72-120">Describe cómo transformar un fragmento de nodo.</span><span class="sxs-lookup"><span data-stu-id="54b72-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="54b72-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="54b72-121">Related Sections</span></span>  
 [<span data-ttu-id="54b72-122">Migración desde la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="54b72-122">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="54b72-123">Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform></span><span class="sxs-lookup"><span data-stu-id="54b72-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b72-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="54b72-124">See also</span></span>

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
