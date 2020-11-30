---
title: Resolución de recursos externos durante el procesamiento XSLT
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 5d50711eda266cecdb817c778f04aa845fa4c342
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686649"
---
# <a name="resolving-external-resources-during-xslt-processing"></a><span data-ttu-id="03338-102">Resolución de recursos externos durante el procesamiento XSLT</span><span class="sxs-lookup"><span data-stu-id="03338-102">Resolving External Resources During XSLT Processing</span></span>

<span data-ttu-id="03338-103">Hay varios momentos a lo largo de una transformación XSLT en los cuales puede que necesite resolver recursos externos.</span><span class="sxs-lookup"><span data-stu-id="03338-103">There are several times during an XSLT transformation when you may need to resolve external resources.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="03338-104">Utilizar la clase XmlResolver</span><span class="sxs-lookup"><span data-stu-id="03338-104">Using the XmlResolver Class</span></span>  

 <span data-ttu-id="03338-105">La clase <xref:System.Xml.XmlResolver> se utiliza para resolver recursos externos.</span><span class="sxs-lookup"><span data-stu-id="03338-105">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="03338-106">En la siguiente tabla se describe cuándo <xref:System.Xml.XmlResolver> se implica en el procesamiento XSLT.</span><span class="sxs-lookup"><span data-stu-id="03338-106">The following table describes when the <xref:System.Xml.XmlResolver> becomes involved during XSLT processing.</span></span>  
  
|<span data-ttu-id="03338-107">Tarea de XSLT</span><span class="sxs-lookup"><span data-stu-id="03338-107">XSLT task</span></span>|<span data-ttu-id="03338-108">XmlResolver se utiliza para</span><span class="sxs-lookup"><span data-stu-id="03338-108">What the XmlResolver is used for</span></span>|  
|---------------|--------------------------------------|  
|<span data-ttu-id="03338-109">Compilar la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="03338-109">Compile the style sheet.</span></span>|<span data-ttu-id="03338-110">Resolver el identificador URI de la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="03338-110">Resolve the URI of the style sheet.</span></span><br /><br /> <span data-ttu-id="03338-111">\- y -</span><span class="sxs-lookup"><span data-stu-id="03338-111">-and-</span></span><br /><br /> <span data-ttu-id="03338-112">Resolver referencias URI en cualquier elemento `xsl:import` o `xsl:include`.</span><span class="sxs-lookup"><span data-stu-id="03338-112">Resolve URI references in any `xsl:import` or `xsl:include` elements.</span></span>|  
|<span data-ttu-id="03338-113">Ejecutar la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="03338-113">Execute the style sheet.</span></span>|<span data-ttu-id="03338-114">Resolver el identificador URI del documento de contexto.</span><span class="sxs-lookup"><span data-stu-id="03338-114">Resolve the URI of the context document.</span></span><br /><br /> <span data-ttu-id="03338-115">\- y -</span><span class="sxs-lookup"><span data-stu-id="03338-115">-and-</span></span><br /><br /> <span data-ttu-id="03338-116">Resolver referencias URI en cualquier función `document()` de XSLT.</span><span class="sxs-lookup"><span data-stu-id="03338-116">Resolve URI references in any XSLT `document()` functions.</span></span>|  
  
 <span data-ttu-id="03338-117">Los métodos <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> y <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> incluyen sobrecargas que toman un objeto <xref:System.Xml.XmlResolver> como uno de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="03338-117">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods include overloads that take an <xref:System.Xml.XmlResolver> object as one of its arguments.</span></span> <span data-ttu-id="03338-118">Si no se especifica un código <xref:System.Xml.XmlResolver>, se utiliza una referencia <xref:System.Xml.XmlUrlResolver> predeterminada sin ninguna credencial.</span><span class="sxs-lookup"><span data-stu-id="03338-118">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
 <span data-ttu-id="03338-119">En la siguiente lista se describe cuándo es conveniente especificar un objeto <xref:System.Xml.XmlResolver>:</span><span class="sxs-lookup"><span data-stu-id="03338-119">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
- <span data-ttu-id="03338-120">Si el proceso XSLT necesita tener acceso a un recurso de red que requiere autenticación, puede utilizar un <xref:System.Xml.XmlResolver> con las credenciales necesarias.</span><span class="sxs-lookup"><span data-stu-id="03338-120">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
- <span data-ttu-id="03338-121">Si desea restringir los recursos a los que tiene acceso el proceso XSLT, puede utilizar un <xref:System.Xml.XmlSecureResolver> con el conjunto de permisos correcto.</span><span class="sxs-lookup"><span data-stu-id="03338-121">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="03338-122">Utilice la clase <xref:System.Xml.XmlSecureResolver> si necesita abrir un recurso que no controla o que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="03338-122">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
- <span data-ttu-id="03338-123">Si desea personalizar el comportamiento, puede implementar su propia clase <xref:System.Xml.XmlResolver> y utilizarla para resolver recursos.</span><span class="sxs-lookup"><span data-stu-id="03338-123">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
- <span data-ttu-id="03338-124">Si desea asegurarse de que no se tiene acceso a ningún recurso externo, puede especificar `null` para el argumento <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="03338-124">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03338-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03338-125">Example</span></span>  

 <span data-ttu-id="03338-126">En el siguiente ejemplo se compila una hoja de estilos que está almacenada en un recurso de red.</span><span class="sxs-lookup"><span data-stu-id="03338-126">The following example compiles a style sheet that is stored on a network resource.</span></span> <span data-ttu-id="03338-127">Un objeto <xref:System.Xml.XmlUrlResolver> especifica las credenciales necesarias para tener acceso a la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="03338-127">An <xref:System.Xml.XmlUrlResolver> object specifies the credentials necessary to access the style sheet.</span></span>  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="03338-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="03338-128">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [<span data-ttu-id="03338-129">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="03338-129">XSLT Transformations</span></span>](xslt-transformations.md)
