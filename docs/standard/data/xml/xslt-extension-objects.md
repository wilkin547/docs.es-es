---
title: Objetos de extensión de XSLT
ms.date: 03/30/2017
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
ms.openlocfilehash: 0e874bb7679854b75a07eb452e47eba0d30807a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720794"
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="e10f3-102">Objetos de extensión de XSLT</span><span class="sxs-lookup"><span data-stu-id="e10f3-102">XSLT Extension Objects</span></span>

<span data-ttu-id="e10f3-103">Los objetos de extensión se utilizan para ampliar la funcionalidad de las hojas de estilos.</span><span class="sxs-lookup"><span data-stu-id="e10f3-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="e10f3-104">La clase <xref:System.Xml.Xsl.XsltArgumentList> mantiene los objetos de extensión.</span><span class="sxs-lookup"><span data-stu-id="e10f3-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="e10f3-105">A continuación se enumeran las ventajas de utilizar un objeto de extensión en lugar de un script incrustado:</span><span class="sxs-lookup"><span data-stu-id="e10f3-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
- <span data-ttu-id="e10f3-106">Proporciona una mejor encapsulación y reutilización de clases.</span><span class="sxs-lookup"><span data-stu-id="e10f3-106">Provides better encapsulation and reuse of classes.</span></span>  
  
- <span data-ttu-id="e10f3-107">Permite que las hojas de estilos sean más pequeñas y facilita su mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="e10f3-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="e10f3-108">Los objetos de extensión XSLT se agregan al objeto <xref:System.Xml.Xsl.XsltArgumentList> con el método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="e10f3-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="e10f3-109">En ese momento se asocian un nombre completo y un identificador URI de espacio de nombres con el objeto de extensión.</span><span class="sxs-lookup"><span data-stu-id="e10f3-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e10f3-110">Se requiere el conjunto de permisos FullTrust para llamar al método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="e10f3-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="e10f3-111">Para obtener más información, vea [Seguridad de acceso del código](../../../framework/misc/code-access-security.md) y [Conjuntos de permisos con nombre](/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e10f3-111">For more information, see [Code Access Security](../../../framework/misc/code-access-security.md) and [Named Permission Sets](/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="e10f3-112">Los tipos de datos devueltos desde los objetos de extensión pertenecen a uno de los cuatro tipos de datos básicos de Xpath: `number`, `string`, `Boolean` y `node set`.</span><span class="sxs-lookup"><span data-stu-id="e10f3-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="e10f3-113">Cualquier método que se defina con la palabra clave `params`, que permite pasar un número no especificado de parámetros, no es compatible actualmente con la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="e10f3-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="e10f3-114">Las hojas de estilos XSLT que utilicen cualquier método definido con la palabra clave `params` no funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="e10f3-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="e10f3-115">Para obtener información, consulte los [parámetros](../../../csharp/language-reference/keywords/params.md).</span><span class="sxs-lookup"><span data-stu-id="e10f3-115">For details, see [params](../../../csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="e10f3-116">Para utilizar un objeto de extensión XSLT</span><span class="sxs-lookup"><span data-stu-id="e10f3-116">To use an XSLT extension object</span></span>  
  
1. <span data-ttu-id="e10f3-117">Cree un objeto <xref:System.Xml.Xsl.XsltArgumentList> y agregue el objeto de extensión utilizando el método <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="e10f3-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2. <span data-ttu-id="e10f3-118">Llame al objeto de extensión desde la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="e10f3-118">Call the extension object from the style sheet.</span></span>  
  
3. <span data-ttu-id="e10f3-119">Pase el objeto <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="e10f3-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10f3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e10f3-120">See also</span></span>

- [<span data-ttu-id="e10f3-121">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="e10f3-121">XSLT Transformations</span></span>](xslt-transformations.md)
- [<span data-ttu-id="e10f3-122">Consideraciones de seguridad de XSLT</span><span class="sxs-lookup"><span data-stu-id="e10f3-122">XSLT Security Considerations</span></span>](xslt-security-considerations.md)
