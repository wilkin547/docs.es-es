---
title: "Resolución de recursos externos durante el procesamiento XSLT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2bb115e14f8ff5d1065d87335d4d9021bd32ddd1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="resolving-external-resources-during-xslt-processing"></a><span data-ttu-id="debdb-102">Resolución de recursos externos durante el procesamiento XSLT</span><span class="sxs-lookup"><span data-stu-id="debdb-102">Resolving External Resources During XSLT Processing</span></span>
<span data-ttu-id="debdb-103">Hay varios momentos a lo largo de una transformación XSLT en los cuales puede que necesite resolver recursos externos.</span><span class="sxs-lookup"><span data-stu-id="debdb-103">There are several times during an XSLT transformation when you may need to resolve external resources.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="debdb-104">Utilizar la clase XmlResolver</span><span class="sxs-lookup"><span data-stu-id="debdb-104">Using the XmlResolver Class</span></span>  
 <span data-ttu-id="debdb-105">La clase <xref:System.Xml.XmlResolver> se utiliza para resolver recursos externos.</span><span class="sxs-lookup"><span data-stu-id="debdb-105">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="debdb-106">En la siguiente tabla se describe cuándo <xref:System.Xml.XmlResolver> se implica en el procesamiento XSLT.</span><span class="sxs-lookup"><span data-stu-id="debdb-106">The following table describes when the <xref:System.Xml.XmlResolver> becomes involved during XSLT processing.</span></span>  
  
|<span data-ttu-id="debdb-107">Tarea de XSLT</span><span class="sxs-lookup"><span data-stu-id="debdb-107">XSLT task</span></span>|<span data-ttu-id="debdb-108">XmlResolver se utiliza para</span><span class="sxs-lookup"><span data-stu-id="debdb-108">What the XmlResolver is used for</span></span>|  
|---------------|--------------------------------------|  
|<span data-ttu-id="debdb-109">Compilar la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="debdb-109">Compile the style sheet.</span></span>|<span data-ttu-id="debdb-110">Resolver el identificador URI de la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="debdb-110">Resolve the URI of the style sheet.</span></span><br /><br /> <span data-ttu-id="debdb-111">- y -</span><span class="sxs-lookup"><span data-stu-id="debdb-111">-and-</span></span><br /><br /> <span data-ttu-id="debdb-112">Resolver referencias URI en cualquier elemento `xsl:import` o `xsl:include`.</span><span class="sxs-lookup"><span data-stu-id="debdb-112">Resolve URI references in any `xsl:import` or `xsl:include` elements.</span></span>|  
|<span data-ttu-id="debdb-113">Ejecutar la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="debdb-113">Execute the style sheet.</span></span>|<span data-ttu-id="debdb-114">Resolver el identificador URI del documento de contexto.</span><span class="sxs-lookup"><span data-stu-id="debdb-114">Resolve the URI of the context document.</span></span><br /><br /> <span data-ttu-id="debdb-115">- y -</span><span class="sxs-lookup"><span data-stu-id="debdb-115">-and-</span></span><br /><br /> <span data-ttu-id="debdb-116">Resolver referencias URI en cualquier función `document()` de XSLT.</span><span class="sxs-lookup"><span data-stu-id="debdb-116">Resolve URI references in any XSLT `document()` functions.</span></span>|  
  
 <span data-ttu-id="debdb-117">Los métodos <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> y <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> incluyen sobrecargas que toman un objeto <xref:System.Xml.XmlResolver> como uno de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="debdb-117">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods include overloads that take an <xref:System.Xml.XmlResolver> object as one of its arguments.</span></span> <span data-ttu-id="debdb-118">Si no se especifica un código <xref:System.Xml.XmlResolver>, se utiliza una referencia <xref:System.Xml.XmlUrlResolver> predeterminada sin ninguna credencial.</span><span class="sxs-lookup"><span data-stu-id="debdb-118">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
 <span data-ttu-id="debdb-119">En la siguiente lista se describe cuándo es conveniente especificar un objeto <xref:System.Xml.XmlResolver>:</span><span class="sxs-lookup"><span data-stu-id="debdb-119">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
-   <span data-ttu-id="debdb-120">Si el proceso XSLT necesita tener acceso a un recurso de red que requiere autenticación, puede utilizar un <xref:System.Xml.XmlResolver> con las credenciales necesarias.</span><span class="sxs-lookup"><span data-stu-id="debdb-120">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
-   <span data-ttu-id="debdb-121">Si desea restringir los recursos a los que tiene acceso el proceso XSLT, puede utilizar un <xref:System.Xml.XmlSecureResolver> con el conjunto de permisos correcto.</span><span class="sxs-lookup"><span data-stu-id="debdb-121">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="debdb-122">Utilice la clase <xref:System.Xml.XmlSecureResolver> si necesita abrir un recurso que no controla o que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="debdb-122">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
-   <span data-ttu-id="debdb-123">Si desea personalizar el comportamiento, puede implementar su propia clase <xref:System.Xml.XmlResolver> y utilizarla para resolver recursos.</span><span class="sxs-lookup"><span data-stu-id="debdb-123">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
-   <span data-ttu-id="debdb-124">Si desea asegurarse de que no se tiene acceso a ningún recurso externo, puede especificar `null` para el argumento <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="debdb-124">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="debdb-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="debdb-125">Example</span></span>  
 <span data-ttu-id="debdb-126">En el siguiente ejemplo se compila una hoja de estilos que está almacenada en un recurso de red.</span><span class="sxs-lookup"><span data-stu-id="debdb-126">The following example compiles a style sheet that is stored on a network resource.</span></span> <span data-ttu-id="debdb-127">Un objeto <xref:System.Xml.XmlUrlResolver> especifica las credenciales necesarias para tener acceso a la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="debdb-127">An <xref:System.Xml.XmlUrlResolver> object specifies the credentials necessary to access the style sheet.</span></span>  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="debdb-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="debdb-128">See Also</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltSettings>  
 [<span data-ttu-id="debdb-129">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="debdb-129">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
