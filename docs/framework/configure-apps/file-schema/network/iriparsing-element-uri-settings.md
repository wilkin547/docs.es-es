---
title: Elemento <iriParsing> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698091"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="073a7-102">\<elemento > Análisisiri (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="073a7-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="073a7-103">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="073a7-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[<span data-ttu-id="073a7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="073a7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="073a7-105">&nbsp;[ **uri de\<&nbsp;>** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="073a7-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="073a7-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<análisisiri >**</span><span class="sxs-lookup"><span data-stu-id="073a7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="073a7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="073a7-107">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="073a7-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="073a7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="073a7-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="073a7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="073a7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="073a7-110">Attributes</span></span>  
  
|<span data-ttu-id="073a7-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="073a7-111">**Element**</span></span>|<span data-ttu-id="073a7-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="073a7-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="073a7-113">Especifica si está habilitado el análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="073a7-113">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="073a7-114">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="073a7-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="073a7-115">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="073a7-115">Child Elements</span></span>  
 <span data-ttu-id="073a7-116">Ninguno</span><span class="sxs-lookup"><span data-stu-id="073a7-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="073a7-117">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="073a7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="073a7-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="073a7-118">**Element**</span></span>|<span data-ttu-id="073a7-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="073a7-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="073a7-120">uri</span><span class="sxs-lookup"><span data-stu-id="073a7-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="073a7-121">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="073a7-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="073a7-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="073a7-122">Remarks</span></span>  
 <span data-ttu-id="073a7-123">La clase de <xref:System.Uri> existente se ha ampliado en .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="073a7-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="073a7-124">3,0 SP1 y 2,0 SP1 para proporcionar compatibilidad con los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="073a7-124">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="073a7-125">Los usuarios actuales no verán ningún cambio en el comportamiento de .NET Framework 2,0 a menos que habiliten específicamente la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="073a7-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="073a7-126">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="073a7-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="073a7-127">Para habilitar la compatibilidad con IRI, se necesitan los dos cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="073a7-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="073a7-128">Agregue la siguiente línea al archivo Machine. config en el directorio .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="073a7-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="073a7-129">Especifique si deben aplicarse las reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="073a7-129">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="073a7-130">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="073a7-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="073a7-131">Al habilitar el análisis de IRI (Análisisiri Enabled = `true`), se realizará la normalización y la comprobación de caracteres según las reglas de IRI más recientes en RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="073a7-131">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="073a7-132">El valor predeterminado es `false` y realizará la normalización y la comprobación de caracteres según RFC 2396 y RFC 3986 (para los literales de IPv6).</span><span class="sxs-lookup"><span data-stu-id="073a7-132">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="073a7-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="073a7-133">Configuration Files</span></span>  
 <span data-ttu-id="073a7-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="073a7-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="073a7-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="073a7-135">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="073a7-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="073a7-136">Description</span></span>  
 <span data-ttu-id="073a7-137">En el ejemplo siguiente se muestra una configuración utilizada por la clase <xref:System.Uri> para admitir el análisis de IRI y los nombres IDN.</span><span class="sxs-lookup"><span data-stu-id="073a7-137">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="073a7-138">Código</span><span class="sxs-lookup"><span data-stu-id="073a7-138">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="073a7-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="073a7-139">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="073a7-140">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="073a7-140">Network Settings Schema</span></span>](index.md)
