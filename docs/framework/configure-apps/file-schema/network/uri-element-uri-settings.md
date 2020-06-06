---
title: Elemento <uri> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697440"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="a57c2-102">Elemento \<uri> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="a57c2-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="a57c2-103">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="a57c2-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="a57c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a57c2-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a57c2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a57c2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a57c2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a57c2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a57c2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a57c2-107">Attributes</span></span>  
 <span data-ttu-id="a57c2-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a57c2-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a57c2-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a57c2-109">Child Elements</span></span>  
  
|<span data-ttu-id="a57c2-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="a57c2-110">**Element**</span></span>|<span data-ttu-id="a57c2-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a57c2-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a57c2-112">IDN</span><span class="sxs-lookup"><span data-stu-id="a57c2-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="a57c2-113">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="a57c2-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="a57c2-114">Análisisiri</span><span class="sxs-lookup"><span data-stu-id="a57c2-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="a57c2-115">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="a57c2-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="a57c2-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="a57c2-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="a57c2-117">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="a57c2-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a57c2-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a57c2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a57c2-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a57c2-119">**Element**</span></span>|<span data-ttu-id="a57c2-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a57c2-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a57c2-121">configuration</span><span class="sxs-lookup"><span data-stu-id="a57c2-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="a57c2-122">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="a57c2-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a57c2-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a57c2-123">Remarks</span></span>  
 <span data-ttu-id="a57c2-124">El `uri` elemento contiene la configuración de los miembros de la <xref:System.Uri> clase utilizada por las clases del <xref:System.Net> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a57c2-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="a57c2-125">La configuración configura la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="a57c2-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a57c2-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a57c2-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a57c2-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="a57c2-127">Description</span></span>  
 <span data-ttu-id="a57c2-128">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="a57c2-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="a57c2-129">En el ejemplo también se borran todos los valores de esquema y, a continuación, se agrega compatibilidad para no escapar los delimitadores de ruta de acceso con codificación porcentual para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="a57c2-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a57c2-130">Código</span><span class="sxs-lookup"><span data-stu-id="a57c2-130">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a57c2-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a57c2-131">See also</span></span>

- [<span data-ttu-id="a57c2-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a57c2-132">Network Settings Schema</span></span>](index.md)
