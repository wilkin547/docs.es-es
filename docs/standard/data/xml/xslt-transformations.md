---
title: Transformaciones XSLT
ms.date: 03/30/2017
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
ms.openlocfilehash: 686b2d454eda99095bcb335c8b0edba9ecf2e304
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685063"
---
# <a name="xslt-transformations"></a><span data-ttu-id="72f26-102">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="72f26-102">XSLT Transformations</span></span>

<span data-ttu-id="72f26-103">El objetivo de XSLT (Extensible Stylesheet Language Transformation) es transformar el contenido de un documento XML de origen en otro documento con un formato o estructura diferentes.</span><span class="sxs-lookup"><span data-stu-id="72f26-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="72f26-104">Por ejemplo, se puede emplear para transformar el documento XML en HTML con el fin de usarlo en un sitio web o transformarlo en un documento que sólo contenga los campos necesarios para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="72f26-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="72f26-105">Las especificaciones de este proceso de transformación se encuentran en la [recomendación W3C XSL Transformations (XSLT) Version 1.0](https://www.w3.org/TR/xslt-10/).</span><span class="sxs-lookup"><span data-stu-id="72f26-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
 <span data-ttu-id="72f26-106">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el procesador XSLT en .NET.</span><span class="sxs-lookup"><span data-stu-id="72f26-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in .NET.</span></span> <span data-ttu-id="72f26-107">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es compatible con la [recomendación XSLT 1.0. del W3C](https://www.w3.org/TR/xslt-10/).</span><span class="sxs-lookup"><span data-stu-id="72f26-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the [W3C XSLT 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72f26-108">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="72f26-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="72f26-109">La clase <xref:System.Xml.Xsl.XslCompiledTransform> es una nueva implementación del motor XSLT.</span><span class="sxs-lookup"><span data-stu-id="72f26-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="72f26-110">Incluye mejoras de rendimiento y nuevas características de seguridad.</span><span class="sxs-lookup"><span data-stu-id="72f26-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="72f26-111">La práctica recomendada es crear aplicaciones XSLT mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="72f26-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72f26-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="72f26-112">In This Section</span></span>  

 [<span data-ttu-id="72f26-113">Uso de la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="72f26-113">Using the XslCompiledTransform Class</span></span>](using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="72f26-114">Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="72f26-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="72f26-115">Migración desde la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="72f26-115">Migrating From the XslTransform Class</span></span>](migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="72f26-116">Describe cómo migrar código desde la clase <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="72f26-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="72f26-117">Compilador XSLT (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="72f26-117">XSLT Compiler (xsltc.exe)</span></span>](xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="72f26-118">Proporciona información sobre cómo utilizar el compilador XSLT.</span><span class="sxs-lookup"><span data-stu-id="72f26-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="72f26-119">Transformaciones XSLT con la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="72f26-119">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="72f26-120">Proporciona información sobre cómo usar la clase <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="72f26-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="72f26-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="72f26-121">Reference</span></span>  

 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltArgumentList>  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="72f26-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="72f26-122">Related Sections</span></span>  

 [<span data-ttu-id="72f26-123">Documentos y datos XML</span><span class="sxs-lookup"><span data-stu-id="72f26-123">XML Documents and Data</span></span>](index.md)
