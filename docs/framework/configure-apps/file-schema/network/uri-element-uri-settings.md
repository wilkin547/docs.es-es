---
title: '&lt;URI&gt; elemento (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 05b2fb4255643f657f37012ec51a1b29ed68095d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742814"
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="6aa44-102">&lt;URI&gt; elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="6aa44-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="6aa44-103">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="6aa44-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="6aa44-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="6aa44-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="6aa44-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="6aa44-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="6aa44-106">\<URI ></span><span class="sxs-lookup"><span data-stu-id="6aa44-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="6aa44-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6aa44-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6aa44-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6aa44-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6aa44-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6aa44-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6aa44-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6aa44-110">Attributes</span></span>  
 <span data-ttu-id="6aa44-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6aa44-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6aa44-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6aa44-112">Child Elements</span></span>  
  
|<span data-ttu-id="6aa44-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="6aa44-113">**Element**</span></span>|<span data-ttu-id="6aa44-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6aa44-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6aa44-115">IDN</span><span class="sxs-lookup"><span data-stu-id="6aa44-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="6aa44-116">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="6aa44-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="6aa44-117">Análisisiri</span><span class="sxs-lookup"><span data-stu-id="6aa44-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="6aa44-118">Especifica si el análisis de identificadores de recursos internacionales (IRI) se aplica a <xref:System.Uri> y si se debe aplicar las reglas de análisis IRI.</span><span class="sxs-lookup"><span data-stu-id="6aa44-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="6aa44-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="6aa44-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="6aa44-120">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="6aa44-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6aa44-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6aa44-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6aa44-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="6aa44-122">**Element**</span></span>|<span data-ttu-id="6aa44-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6aa44-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6aa44-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="6aa44-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="6aa44-125">Contiene valores para todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6aa44-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6aa44-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6aa44-126">Remarks</span></span>  
 <span data-ttu-id="6aa44-127">El `uri` elemento contiene los valores para los miembros de la <xref:System.Uri> clase utilizada por clases en el <xref:System.Net> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6aa44-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="6aa44-128">La configuración de configura la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="6aa44-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa44-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6aa44-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6aa44-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="6aa44-130">Description</span></span>  
 <span data-ttu-id="6aa44-131">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="6aa44-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="6aa44-132">El ejemplo también borra todos los valores de esquema y, a continuación, agrega compatibilidad para delimitadores de ruta de acceso con codificación de porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="6aa44-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6aa44-133">Código</span><span class="sxs-lookup"><span data-stu-id="6aa44-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6aa44-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aa44-134">See Also</span></span>  
 [<span data-ttu-id="6aa44-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="6aa44-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
