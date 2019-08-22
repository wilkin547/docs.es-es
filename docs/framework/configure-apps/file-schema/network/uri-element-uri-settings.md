---
title: Elemento <Uri> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 80d71da5ca680872e4948fa8ff135fbbdf08cffe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663964"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="a0e23-102">\<Elemento URI > (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="a0e23-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="a0e23-103">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="a0e23-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="a0e23-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="a0e23-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="a0e23-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="a0e23-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="a0e23-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="a0e23-106">\<uri></span></span>](uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="a0e23-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0e23-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0e23-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0e23-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0e23-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0e23-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0e23-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0e23-110">Attributes</span></span>  
 <span data-ttu-id="a0e23-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a0e23-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0e23-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0e23-112">Child Elements</span></span>  
  
|<span data-ttu-id="a0e23-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="a0e23-113">**Element**</span></span>|<span data-ttu-id="a0e23-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a0e23-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a0e23-115">idn</span><span class="sxs-lookup"><span data-stu-id="a0e23-115">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="a0e23-116">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="a0e23-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="a0e23-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="a0e23-117">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="a0e23-118">Especifica si se aplica el análisis de identificadores de recursos internacionales ( <xref:System.Uri> IRI) y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="a0e23-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="a0e23-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="a0e23-119">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="a0e23-120">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="a0e23-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0e23-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0e23-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a0e23-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="a0e23-122">**Element**</span></span>|<span data-ttu-id="a0e23-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a0e23-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a0e23-124">configuration</span><span class="sxs-lookup"><span data-stu-id="a0e23-124">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="a0e23-125">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0e23-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0e23-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0e23-126">Remarks</span></span>  
 <span data-ttu-id="a0e23-127">El `uri` elemento contiene la configuración de los miembros <xref:System.Uri> de la clase <xref:System.Net> utilizada por las clases del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0e23-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="a0e23-128">La configuración configura la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="a0e23-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0e23-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0e23-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a0e23-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a0e23-130">Description</span></span>  
 <span data-ttu-id="a0e23-131">En el ejemplo siguiente se muestra una configuración utilizada <xref:System.Uri> por la clase para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="a0e23-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="a0e23-132">En el ejemplo también se borran todos los valores de esquema y, a continuación, se agrega compatibilidad para no escapar los delimitadores de ruta de acceso con codificación porcentual para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="a0e23-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a0e23-133">Código</span><span class="sxs-lookup"><span data-stu-id="a0e23-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0e23-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0e23-134">See also</span></span>

- [<span data-ttu-id="a0e23-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a0e23-135">Network Settings Schema</span></span>](index.md)
