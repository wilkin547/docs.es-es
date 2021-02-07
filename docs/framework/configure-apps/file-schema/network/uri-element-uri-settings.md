---
description: 'Más información sobre: <uri> elemento (configuración de URI)'
title: Elemento <uri> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: dc30778fdf5babfb87da0e32829ed9a3ae412c2e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740124"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="1c686-103">Elemento \<uri> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="1c686-103">\<uri> Element (Uri Settings)</span></span>

<span data-ttu-id="1c686-104">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="1c686-104">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="1c686-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c686-105">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c686-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1c686-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1c686-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1c686-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c686-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1c686-108">Attributes</span></span>  

 <span data-ttu-id="1c686-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1c686-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c686-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1c686-110">Child Elements</span></span>  
  
|<span data-ttu-id="1c686-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="1c686-111">**Element**</span></span>|<span data-ttu-id="1c686-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1c686-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1c686-113">IDN</span><span class="sxs-lookup"><span data-stu-id="1c686-113">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="1c686-114">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="1c686-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="1c686-115">Análisisiri</span><span class="sxs-lookup"><span data-stu-id="1c686-115">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="1c686-116">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="1c686-116">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="1c686-117">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="1c686-117">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="1c686-118">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="1c686-118">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c686-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1c686-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1c686-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="1c686-120">**Element**</span></span>|<span data-ttu-id="1c686-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1c686-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1c686-122">configuration</span><span class="sxs-lookup"><span data-stu-id="1c686-122">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="1c686-123">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c686-123">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c686-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1c686-124">Remarks</span></span>  

 <span data-ttu-id="1c686-125">El `uri` elemento contiene la configuración de los miembros de la <xref:System.Uri> clase utilizada por las clases del <xref:System.Net> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c686-125">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="1c686-126">La configuración configura la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="1c686-126">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c686-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c686-127">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1c686-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c686-128">Description</span></span>  

 <span data-ttu-id="1c686-129">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="1c686-129">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="1c686-130">En el ejemplo también se borran todos los valores de esquema y, a continuación, se agrega compatibilidad para no escapar los delimitadores de ruta de acceso con codificación porcentual para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="1c686-130">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1c686-131">Código</span><span class="sxs-lookup"><span data-stu-id="1c686-131">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1c686-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c686-132">See also</span></span>

- [<span data-ttu-id="1c686-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="1c686-133">Network Settings Schema</span></span>](index.md)
