---
title: Elemento <httpListener> (configuración de red)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088375"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="f3a6f-102">Elemento \<httpListener> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="f3a6f-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="f3a6f-103">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**

## <a name="syntax"></a><span data-ttu-id="f3a6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3a6f-104">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="f3a6f-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="f3a6f-105">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3a6f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f3a6f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f3a6f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3a6f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f3a6f-108">Attributes</span></span>  
  
|<span data-ttu-id="f3a6f-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="f3a6f-109">Attribute</span></span>|<span data-ttu-id="f3a6f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3a6f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3a6f-111">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="f3a6f-111">unescapeRequestUrl</span></span>|<span data-ttu-id="f3a6f-112">Valor booleano que indica si una <xref:System.Net.HttpListener> instancia de usa el URI sin escape sin formato en lugar del URI convertido.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-112">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3a6f-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f3a6f-113">Child Elements</span></span>  
 <span data-ttu-id="f3a6f-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3a6f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f3a6f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f3a6f-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="f3a6f-116">**Element**</span></span>|<span data-ttu-id="f3a6f-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f3a6f-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f3a6f-118">settings</span><span class="sxs-lookup"><span data-stu-id="f3a6f-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="f3a6f-119">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3a6f-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3a6f-120">Remarks</span></span>  
 <span data-ttu-id="f3a6f-121">El atributo **unescapeRequestUrl** indica si <xref:System.Net.HttpListener> usa el URI sin escape sin formato en lugar del URI convertido en el que se convierten los valores con codificación porcentual y se toman otros pasos de normalización.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-121">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="f3a6f-122">Cuando una <xref:System.Net.HttpListener> instancia recibe una solicitud a través del `http.sys` servicio, crea una instancia de la cadena URI proporcionada por `http.sys` y la expone como la <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-122">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="f3a6f-123">El `http.sys` servicio expone dos cadenas URI de solicitud:</span><span class="sxs-lookup"><span data-stu-id="f3a6f-123">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="f3a6f-124">URI sin formato</span><span class="sxs-lookup"><span data-stu-id="f3a6f-124">Raw URI</span></span>  
  
- <span data-ttu-id="f3a6f-125">URI convertido</span><span class="sxs-lookup"><span data-stu-id="f3a6f-125">Converted URI</span></span>  
  
 <span data-ttu-id="f3a6f-126">El URI sin formato es el <xref:System.Uri?displayProperty=nameWithType> proporcionado en la línea de solicitud de una solicitud http:</span><span class="sxs-lookup"><span data-stu-id="f3a6f-126">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="f3a6f-127">El URI sin formato proporcionado por `http.sys` para la solicitud mencionada anteriormente es "/path/".</span><span class="sxs-lookup"><span data-stu-id="f3a6f-127">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="f3a6f-128">Representa la cadena que sigue al verbo HTTP tal como se envió a través de la red.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-128">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="f3a6f-129">El `http.sys` servicio crea un URI convertido a partir de la información proporcionada en la solicitud mediante el URI proporcionado en la línea de solicitud HTTP y el encabezado de host para determinar el servidor de origen al que se debe reenviar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-129">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="f3a6f-130">Para ello, se compara la información de la solicitud con un conjunto de prefijos de URI registrados.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-130">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="f3a6f-131">La documentación del SDK del servidor HTTP hace referencia a este URI convertido como la estructura HTTP_COOKED_URL.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-131">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="f3a6f-132">Para poder comparar la solicitud con prefijos URI registrados, es necesario realizar alguna normalización a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-132">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="f3a6f-133">Para el ejemplo anterior, el URI convertido sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="f3a6f-133">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="f3a6f-134">El `http.sys` servicio combina el <xref:System.Uri.Host%2A?displayProperty=nameWithType> valor de propiedad y la cadena en la línea de solicitud para crear un URI convertido.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-134">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="f3a6f-135">Además, `http.sys` la <xref:System.Uri?displayProperty=nameWithType> clase también hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3a6f-135">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="f3a6f-136">Quita la escape de todos los valores codificados por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-136">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="f3a6f-137">Convierte los caracteres que no son ASCII con codificación porcentual en una representación de caracteres UTF-16.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-137">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="f3a6f-138">Tenga en cuenta que se admiten los caracteres UTF-8 y ANSI/DBCS, así como caracteres Unicode (codificación Unicode con el formato% uXXXX).</span><span class="sxs-lookup"><span data-stu-id="f3a6f-138">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="f3a6f-139">Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-139">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="f3a6f-140">Dado que la solicitud no contiene ninguna información sobre la codificación utilizada para los valores codificados con porcentaje, es posible que no sea posible determinar la codificación correcta solo mediante el análisis de los valores codificados por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-140">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="f3a6f-141">Por lo tanto, `http.sys` proporciona dos claves del registro para modificar el proceso:</span><span class="sxs-lookup"><span data-stu-id="f3a6f-141">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="f3a6f-142">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="f3a6f-142">Registry Key</span></span>|<span data-ttu-id="f3a6f-143">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="f3a6f-143">Default Value</span></span>|<span data-ttu-id="f3a6f-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3a6f-144">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="f3a6f-145">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="f3a6f-145">EnableNonUTF8</span></span>|<span data-ttu-id="f3a6f-146">1</span><span class="sxs-lookup"><span data-stu-id="f3a6f-146">1</span></span>|<span data-ttu-id="f3a6f-147">Si es cero, `http.sys` solo acepta direcciones URL con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-147">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="f3a6f-148">Si es distinto de cero, `http.sys` también acepta direcciones URL codificadas en ANSI o codificadas con DBCS en las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-148">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="f3a6f-149">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="f3a6f-149">FavorUTF8</span></span>|<span data-ttu-id="f3a6f-150">1</span><span class="sxs-lookup"><span data-stu-id="f3a6f-150">1</span></span>|<span data-ttu-id="f3a6f-151">Si es distinto de cero, `http.sys` siempre intenta descodificar una dirección URL como UTF-8 primero; si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, http. sys intenta descodificarlo como ANSI o DBCS.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-151">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="f3a6f-152">Si cero (y EnableNonUTF8 es distinto de cero), `http.sys` intenta descodificarlo como ANSI o DBCS; si no se realiza correctamente, intenta una conversión UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-152">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="f3a6f-153">Cuando <xref:System.Net.HttpListener> recibe una solicitud, utiliza el URI convertido de `http.sys` como entrada para la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-153">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="f3a6f-154">Hay una necesidad de admitir caracteres además de caracteres y números en los URI.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-154">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="f3a6f-155">Un ejemplo es el URI siguiente, que se usa para recuperar información de cliente para el número de cliente "1/3812":</span><span class="sxs-lookup"><span data-stu-id="f3a6f-155">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="f3a6f-156">Observe la barra diagonal codificada en porcentaje en el URI (% 2F).</span><span class="sxs-lookup"><span data-stu-id="f3a6f-156">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="f3a6f-157">Esto es necesario, ya que en este caso el carácter de barra diagonal representa datos y no un delimitador de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-157">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="f3a6f-158">Al pasar la cadena al constructor URI se conducirá al URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3a6f-158">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="f3a6f-159">La división de la ruta de acceso en sus segmentos daría lugar a los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="f3a6f-159">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="f3a6f-160">No se trata de la intención del remitente de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-160">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="f3a6f-161">Si el atributo **unescapeRequestUrl** se establece en **false**, cuando <xref:System.Net.HttpListener> recibe una solicitud, usa el URI sin formato en lugar del URI convertido desde `http.sys` como entrada a la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-161">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="f3a6f-162">El valor predeterminado para el atributo **unescapeRequestUrl** es **true**.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-162">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="f3a6f-163">La <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> propiedad se puede utilizar para obtener el valor actual del atributo **unescapeRequestUrl** de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-163">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3a6f-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3a6f-164">Example</span></span>  
 <span data-ttu-id="f3a6f-165">En el ejemplo siguiente se muestra cómo configurar la <xref:System.Net.HttpListener> clase cuando recibe una solicitud para usar el URI sin formato en lugar del URI convertido desde `http.sys` como entrada a la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3a6f-165">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="f3a6f-166">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="f3a6f-166">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="f3a6f-167">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f3a6f-167">Namespace</span></span>|<span data-ttu-id="f3a6f-168">System.Net</span><span class="sxs-lookup"><span data-stu-id="f3a6f-168">System.Net</span></span>|  
|<span data-ttu-id="f3a6f-169">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="f3a6f-169">Schema Name</span></span>||  
|<span data-ttu-id="f3a6f-170">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="f3a6f-170">Validation File</span></span>||  
|<span data-ttu-id="f3a6f-171">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="f3a6f-171">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="f3a6f-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3a6f-172">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="f3a6f-173">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f3a6f-173">Network Settings Schema</span></span>](index.md)
