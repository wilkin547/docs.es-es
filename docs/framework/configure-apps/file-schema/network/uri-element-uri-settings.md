---
title: Elemento <uri> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697440"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="f91d3-102">\<URI > elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="f91d3-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="f91d3-103">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="f91d3-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[<span data-ttu-id="f91d3-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f91d3-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f91d3-105">&nbsp;**URI de\<&nbsp;>**</span><span class="sxs-lookup"><span data-stu-id="f91d3-105">&nbsp;&nbsp;**\<uri>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f91d3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f91d3-106">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f91d3-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f91d3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f91d3-108">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f91d3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f91d3-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f91d3-109">Attributes</span></span>  
 <span data-ttu-id="f91d3-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f91d3-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f91d3-111">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="f91d3-111">Child Elements</span></span>  
  
|<span data-ttu-id="f91d3-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="f91d3-112">**Element**</span></span>|<span data-ttu-id="f91d3-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f91d3-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f91d3-114">idn</span><span class="sxs-lookup"><span data-stu-id="f91d3-114">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="f91d3-115">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="f91d3-115">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="f91d3-116">iriParsing</span><span class="sxs-lookup"><span data-stu-id="f91d3-116">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="f91d3-117">Especifica si el análisis de identificadores de recursos internacionales (IRI) se aplica a <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="f91d3-117">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="f91d3-118">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="f91d3-118">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="f91d3-119">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="f91d3-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f91d3-120">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="f91d3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f91d3-121">**Element**</span><span class="sxs-lookup"><span data-stu-id="f91d3-121">**Element**</span></span>|<span data-ttu-id="f91d3-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f91d3-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f91d3-123">configuration</span><span class="sxs-lookup"><span data-stu-id="f91d3-123">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="f91d3-124">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="f91d3-124">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f91d3-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f91d3-125">Remarks</span></span>  
 <span data-ttu-id="f91d3-126">El elemento `uri` contiene la configuración de los miembros de la clase <xref:System.Uri> utilizada por las clases del espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="f91d3-126">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="f91d3-127">La configuración configura la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="f91d3-127">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f91d3-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f91d3-128">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f91d3-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="f91d3-129">Description</span></span>  
 <span data-ttu-id="f91d3-130">En el ejemplo siguiente se muestra una configuración utilizada por la clase <xref:System.Uri> para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="f91d3-130">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="f91d3-131">En el ejemplo también se borran todos los valores de esquema y, a continuación, se agrega compatibilidad para no escapar los delimitadores de ruta de acceso con codificación porcentual para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="f91d3-131">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f91d3-132">Código</span><span class="sxs-lookup"><span data-stu-id="f91d3-132">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f91d3-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f91d3-133">See also</span></span>

- [<span data-ttu-id="f91d3-134">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f91d3-134">Network Settings Schema</span></span>](index.md)
