---
title: Transformaciones XSLT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d7fa8492487daff68fd8ebaf4159dd537d13e51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-transformations"></a><span data-ttu-id="8cd6c-102">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="8cd6c-102">XSLT Transformations</span></span>
<span data-ttu-id="8cd6c-103">El objetivo de XSLT (Extensible Stylesheet Language Transformation) es transformar el contenido de un documento XML de origen en otro documento con un formato o estructura diferentes.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="8cd6c-104">Por ejemplo, se puede emplear para transformar el documento XML en HTML con el fin de usarlo en un sitio web o transformarlo en un documento que sólo contenga los campos necesarios para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="8cd6c-105">Este proceso de transformación está especificado por el [recomendación W3C XSL Transformations (XSLT) versión 1.0](http://go.microsoft.com/fwlink/?LinkID=49919).</span><span class="sxs-lookup"><span data-stu-id="8cd6c-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](http://go.microsoft.com/fwlink/?LinkID=49919).</span></span>  
  
 <span data-ttu-id="8cd6c-106">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in the .NET Framework.</span></span> <span data-ttu-id="8cd6c-107">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es compatible con la recomendación XSLT 1.0. del W3C mencionada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the W3C XSLT 1.0 recommendation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cd6c-108">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="8cd6c-109">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es una nueva implementación del motor XSLT.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="8cd6c-110">Incluye mejoras de rendimiento y nuevas características de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="8cd6c-111">La práctica recomendada es crear aplicaciones XSLT mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8cd6c-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8cd6c-112">In This Section</span></span>  
 [<span data-ttu-id="8cd6c-113">Uso de la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="8cd6c-113">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="8cd6c-114">Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="8cd6c-115">Migración desde la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="8cd6c-115">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="8cd6c-116">Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="8cd6c-117">Compilador XSLT (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="8cd6c-117">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="8cd6c-118">Proporciona información sobre cómo utilizar el compilador XSLT.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="8cd6c-119">Transformaciones XSLT con la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="8cd6c-119">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="8cd6c-120">Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 <span data-ttu-id="8cd6c-121">**Tenga en cuenta** la <xref:System.Xml.Xsl.XslTransform> clase está obsoleta en la versión de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="8cd6c-121">**Note** The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0 release.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8cd6c-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="8cd6c-122">Reference</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="8cd6c-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8cd6c-123">Related Sections</span></span>  
 [<span data-ttu-id="8cd6c-124">Documentos y datos XML</span><span class="sxs-lookup"><span data-stu-id="8cd6c-124">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
