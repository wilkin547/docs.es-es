---
title: Uso de la clase XslCompiledTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a00ae5a2f54aee3d6ac16d0870f9171fe42ca289
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="7f672-102">Uso de la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="7f672-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="7f672-103">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT de Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f672-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="7f672-104">Esta clase se utiliza para compilar hojas de estilos y ejecutar transformaciones XSLT.</span><span class="sxs-lookup"><span data-stu-id="7f672-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f672-105">Aunque el rendimiento total de la clase <xref:System.Xml.Xsl.XslCompiledTransform> es mejor que la clase <xref:System.Xml.Xsl.XslTransform>, el método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslCompiledTransform> podría ser más lento que el método <xref:System.Xml.Xsl.XslTransform.Load%2A> de la clase <xref:System.Xml.Xsl.XslTransform> cuando se le llama por primera vez para una transformación.</span><span class="sxs-lookup"><span data-stu-id="7f672-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="7f672-106">Esto se debe a que el archivo XSLT debe compilarse antes de cargarse.</span><span class="sxs-lookup"><span data-stu-id="7f672-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="7f672-107">Para obtener más información, vea el siguiente blog: [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/) (¿XslCompiledTransform es más lento que XslTransform?).</span><span class="sxs-lookup"><span data-stu-id="7f672-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f672-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7f672-108">In This Section</span></span>  
 [<span data-ttu-id="7f672-109">Entradas en la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="7f672-109">Inputs to the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="7f672-110">Describe las opciones de entrada XSLT disponibles.</span><span class="sxs-lookup"><span data-stu-id="7f672-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="7f672-111">Opciones de salida en la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="7f672-111">Output Options on the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="7f672-112">Describe las opciones de salida XSLT disponibles.</span><span class="sxs-lookup"><span data-stu-id="7f672-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="7f672-113">Resolución de recursos externos durante el procesamiento XSLT</span><span class="sxs-lookup"><span data-stu-id="7f672-113">Resolving External Resources During XSLT Processing</span></span>](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="7f672-114">Describe el uso de la clase <xref:System.Xml.XmlResolver> para resolver recursos externos.</span><span class="sxs-lookup"><span data-stu-id="7f672-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="7f672-115">Extensión de hojas de estilos SXLT</span><span class="sxs-lookup"><span data-stu-id="7f672-115">Extending XSLT Style Sheets</span></span>](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 <span data-ttu-id="7f672-116">Describe cómo se admiten las extensiones XSLT.</span><span class="sxs-lookup"><span data-stu-id="7f672-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="7f672-117">Errores XSLT recuperables</span><span class="sxs-lookup"><span data-stu-id="7f672-117">Recoverable XSLT Errors</span></span>](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|<span data-ttu-id="7f672-118">Enumera cada uno de los comportamientos discrecionales que permite la recomendación XSLT 1.0 del W3C y describe cómo la clase <xref:System.Xml.Xsl.XslCompiledTransform> controla estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="7f672-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="7f672-119">Transformación de un fragmento de nodo</span><span class="sxs-lookup"><span data-stu-id="7f672-119">How to: Transform a Node Fragment</span></span>](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|<span data-ttu-id="7f672-120">Describe cómo transformar un fragmento de nodo.</span><span class="sxs-lookup"><span data-stu-id="7f672-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="7f672-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7f672-121">Related Sections</span></span>  
 [<span data-ttu-id="7f672-122">Migración desde la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="7f672-122">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="7f672-123">Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform></span><span class="sxs-lookup"><span data-stu-id="7f672-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f672-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f672-124">See Also</span></span>  
 <xref:System.Xml.Xsl.XsltSettings>  
 <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
