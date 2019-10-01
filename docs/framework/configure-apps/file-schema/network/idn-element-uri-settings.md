---
title: Elemento <idn> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698172"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="5774f-102">\<idn (elemento de >) (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="5774f-102">\<idn> Element (Uri Settings)</span></span>

<span data-ttu-id="5774f-103">Especifica si el análisis de nombres de dominio internacionalizados (IDN) se aplica a un nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="5774f-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>
  
[<span data-ttu-id="5774f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5774f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="5774f-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5774f-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="5774f-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<idn >**</span><span class="sxs-lookup"><span data-stu-id="5774f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5774f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5774f-107">Syntax</span></span>  
  
```xml
<idn
  enabled="All|AllExceptIntranet|None"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5774f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5774f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5774f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5774f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5774f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5774f-110">Attributes</span></span>  

|<span data-ttu-id="5774f-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="5774f-111">**Element**</span></span>|<span data-ttu-id="5774f-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5774f-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="5774f-113">Especifica si el análisis de nombres de dominio internacionalizados (IDN) se aplica a un nombre de dominio. el valor predeterminado es None.</span><span class="sxs-lookup"><span data-stu-id="5774f-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="5774f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5774f-114">Child elements</span></span>

<span data-ttu-id="5774f-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5774f-115">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="5774f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5774f-116">Parent elements</span></span>

|<span data-ttu-id="5774f-117">**Element**</span><span class="sxs-lookup"><span data-stu-id="5774f-117">**Element**</span></span>|<span data-ttu-id="5774f-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5774f-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5774f-119">uri</span><span class="sxs-lookup"><span data-stu-id="5774f-119">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="5774f-120">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="5774f-120">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  

## <a name="remarks"></a><span data-ttu-id="5774f-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5774f-121">Remarks</span></span>

<span data-ttu-id="5774f-122">La clase <xref:System.Uri> existente se ha ampliado en .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="5774f-122">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="5774f-123">3,0 SP1 y 2,0 SP1 compatible con los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="5774f-123">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="5774f-124">Los usuarios actuales no verán ningún cambio en el comportamiento de .NET Framework 2,0 a menos que habiliten específicamente la compatibilidad con IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="5774f-124">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="5774f-125">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5774f-125">This ensures application compatibility with prior versions of the .NET Framework.</span></span>

<span data-ttu-id="5774f-126">Para habilitar la compatibilidad con IRI, se necesitan los dos cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="5774f-126">To enable support for IRI, the following two changes are required:</span></span>

1. <span data-ttu-id="5774f-127">Agregue la siguiente línea al archivo Machine. config en el directorio .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="5774f-127">Add the following line to the machine.config file under the .NET Framework 2.0 directory:</span></span>
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="5774f-128">Especifique si desea que se aplique el análisis de nombres de dominio internacionalizados (IDN) al nombre de dominio y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="5774f-128">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="5774f-129">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="5774f-129">This can be done in the machine.config or in the app.config file.</span></span>

 <span data-ttu-id="5774f-130">Hay tres valores posibles para IDN en función de los servidores DNS que se usan:</span><span class="sxs-lookup"><span data-stu-id="5774f-130">There are three possible values for IDN depending on the DNS servers that are used:</span></span>

- <span data-ttu-id="5774f-131">IDN habilitado = All</span><span class="sxs-lookup"><span data-stu-id="5774f-131">idn enabled = All</span></span>  

     <span data-ttu-id="5774f-132">Este valor convertirá los nombres de dominio Unicode en sus equivalentes Punycode (nombres IDN).</span><span class="sxs-lookup"><span data-stu-id="5774f-132">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>

- <span data-ttu-id="5774f-133">IDN habilitado = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="5774f-133">idn enabled = AllExceptIntranet</span></span>

     <span data-ttu-id="5774f-134">Este valor convertirá todos los nombres de dominio Unicode que no estén en la Intranet local para usar los equivalentes Punycode (nombres IDN).</span><span class="sxs-lookup"><span data-stu-id="5774f-134">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="5774f-135">En este caso, para administrar nombres internacionales en la Intranet local, los servidores DNS que se usan para la intranet deben admitir la resolución de nombres Unicode.</span><span class="sxs-lookup"><span data-stu-id="5774f-135">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>

- <span data-ttu-id="5774f-136">IDN habilitado = ninguno</span><span class="sxs-lookup"><span data-stu-id="5774f-136">idn enabled = None</span></span>

     <span data-ttu-id="5774f-137">Este valor no convertirá ningún nombre de dominio Unicode para usar Punycode.</span><span class="sxs-lookup"><span data-stu-id="5774f-137">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="5774f-138">Este es el valor predeterminado, que es coherente con el comportamiento de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="5774f-138">This is the default value which is consistent with the .NET Framework 2.0 behavior.</span></span>

 <span data-ttu-id="5774f-139">La activación de IDN convertirá todas la etiquetas Unicode de un nombre de dominio en sus equivalentes de Punycode.</span><span class="sxs-lookup"><span data-stu-id="5774f-139">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="5774f-140">Los nombres de Punycode solo contienen caracteres ASCII y siempre empiezan con el prefijo xn--.</span><span class="sxs-lookup"><span data-stu-id="5774f-140">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="5774f-141">De este modo, se admiten los servidores DNS existentes en Internet, ya que la mayoría de los servidores DNS solo admite caracteres ASCII (vea RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="5774f-141">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>

### <a name="configuration-files"></a><span data-ttu-id="5774f-142">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5774f-142">Configuration files</span></span>

<span data-ttu-id="5774f-143">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5774f-143">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="5774f-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5774f-144">Example</span></span>

<span data-ttu-id="5774f-145">En el ejemplo siguiente se muestra una configuración utilizada por la clase <xref:System.Uri> para admitir el análisis de IRI y los nombres IDN:</span><span class="sxs-lookup"><span data-stu-id="5774f-145">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names:</span></span>

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5774f-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="5774f-146">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="5774f-147">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5774f-147">Network Settings Schema</span></span>](index.md)
