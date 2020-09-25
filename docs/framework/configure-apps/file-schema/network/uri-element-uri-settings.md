---
title: Elemento <uri> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 2f22d70407d10dbb38f0cb8d3a8ac74ff3fe8763
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190207"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="d0c0e-102">Elemento \<uri> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="d0c0e-102">\<uri> Element (Uri Settings)</span></span>

<span data-ttu-id="d0c0e-103">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="d0c0e-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="d0c0e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0c0e-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0c0e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d0c0e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d0c0e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0c0e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d0c0e-107">Attributes</span></span>  

 <span data-ttu-id="d0c0e-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0c0e-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d0c0e-109">Child Elements</span></span>  
  
|<span data-ttu-id="d0c0e-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="d0c0e-110">**Element**</span></span>|<span data-ttu-id="d0c0e-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d0c0e-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d0c0e-112">IDN</span><span class="sxs-lookup"><span data-stu-id="d0c0e-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="d0c0e-113">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="d0c0e-114">Análisisiri</span><span class="sxs-lookup"><span data-stu-id="d0c0e-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="d0c0e-115">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="d0c0e-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="d0c0e-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="d0c0e-117">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0c0e-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d0c0e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d0c0e-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="d0c0e-119">**Element**</span></span>|<span data-ttu-id="d0c0e-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d0c0e-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d0c0e-121">configuration</span><span class="sxs-lookup"><span data-stu-id="d0c0e-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="d0c0e-122">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0c0e-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d0c0e-123">Remarks</span></span>  

 <span data-ttu-id="d0c0e-124">El `uri` elemento contiene la configuración de los miembros de la <xref:System.Uri> clase utilizada por las clases del <xref:System.Net> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="d0c0e-125">La configuración configura la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0c0e-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0c0e-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d0c0e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0c0e-127">Description</span></span>  

 <span data-ttu-id="d0c0e-128">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="d0c0e-129">En el ejemplo también se borran todos los valores de esquema y, a continuación, se agrega compatibilidad para no escapar los delimitadores de ruta de acceso con codificación porcentual para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="d0c0e-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0c0e-130">Código</span><span class="sxs-lookup"><span data-stu-id="d0c0e-130">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0c0e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0c0e-131">See also</span></span>

- [<span data-ttu-id="d0c0e-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d0c0e-132">Network Settings Schema</span></span>](index.md)
