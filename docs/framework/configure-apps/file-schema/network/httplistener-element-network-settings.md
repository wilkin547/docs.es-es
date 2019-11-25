---
title: Elemento <httpListener> (configuración de red)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088375"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="76079-102">\<elemento > httpListener (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="76079-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="76079-103">Personaliza los parámetros utilizados por la clase <xref:System.Net.HttpListener>.</span><span class="sxs-lookup"><span data-stu-id="76079-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

<span data-ttu-id="76079-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76079-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="76079-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="76079-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="76079-106">&nbsp;&nbsp;[ \**&nbsp;&nbsp;\<\** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="76079-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\</span></span>
<span data-ttu-id="76079-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpListener >**</span><span class="sxs-lookup"><span data-stu-id="76079-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**</span></span>

## <a name="syntax"></a><span data-ttu-id="76079-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76079-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="76079-109">Type</span><span class="sxs-lookup"><span data-stu-id="76079-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76079-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76079-110">Attributes and Elements</span></span>  
 <span data-ttu-id="76079-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76079-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76079-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="76079-112">Attributes</span></span>  
  
|<span data-ttu-id="76079-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="76079-113">Attribute</span></span>|<span data-ttu-id="76079-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="76079-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76079-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="76079-115">unescapeRequestUrl</span></span>|<span data-ttu-id="76079-116">Valor booleano que indica si una instancia de <xref:System.Net.HttpListener> usa el URI sin escape sin formato en lugar del URI convertido.</span><span class="sxs-lookup"><span data-stu-id="76079-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76079-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76079-117">Child Elements</span></span>  
 <span data-ttu-id="76079-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="76079-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76079-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76079-119">Parent Elements</span></span>  
  
|<span data-ttu-id="76079-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="76079-120">**Element**</span></span>|<span data-ttu-id="76079-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="76079-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="76079-122">Configuración</span><span class="sxs-lookup"><span data-stu-id="76079-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="76079-123">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="76079-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76079-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76079-124">Remarks</span></span>  
 <span data-ttu-id="76079-125">El atributo **unescapeRequestUrl** indica si <xref:System.Net.HttpListener> usa el URI sin secuencias de escape sin formato en lugar del URI convertido en el que se convierten los valores con codificación porcentual y se toman otros pasos de normalización.</span><span class="sxs-lookup"><span data-stu-id="76079-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="76079-126">Cuando una instancia de <xref:System.Net.HttpListener> recibe una solicitud a través del servicio `http.sys`, crea una instancia de la cadena URI proporcionada por `http.sys`y la expone como la propiedad <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76079-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="76079-127">El servicio `http.sys` expone dos cadenas URI de solicitud:</span><span class="sxs-lookup"><span data-stu-id="76079-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="76079-128">URI sin formato</span><span class="sxs-lookup"><span data-stu-id="76079-128">Raw URI</span></span>  
  
- <span data-ttu-id="76079-129">URI convertido</span><span class="sxs-lookup"><span data-stu-id="76079-129">Converted URI</span></span>  
  
 <span data-ttu-id="76079-130">El URI sin formato es el <xref:System.Uri?displayProperty=nameWithType> proporcionado en la línea de solicitud de una solicitud HTTP:</span><span class="sxs-lookup"><span data-stu-id="76079-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="76079-131">El URI sin formato proporcionado por `http.sys` para la solicitud mencionada anteriormente, es "/path/".</span><span class="sxs-lookup"><span data-stu-id="76079-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="76079-132">Representa la cadena que sigue al verbo HTTP tal como se envió a través de la red.</span><span class="sxs-lookup"><span data-stu-id="76079-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="76079-133">El servicio `http.sys` crea un URI convertido a partir de la información proporcionada en la solicitud mediante el URI proporcionado en la línea de solicitud HTTP y el encabezado de host para determinar el servidor de origen al que se debe reenviar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="76079-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="76079-134">Para ello, se compara la información de la solicitud con un conjunto de prefijos de URI registrados.</span><span class="sxs-lookup"><span data-stu-id="76079-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="76079-135">La documentación del SDK del servidor HTTP hace referencia a este URI convertido como la estructura HTTP_COOKED_URL.</span><span class="sxs-lookup"><span data-stu-id="76079-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="76079-136">Para poder comparar la solicitud con prefijos URI registrados, es necesario realizar alguna normalización a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="76079-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="76079-137">Para el ejemplo anterior, el URI convertido sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="76079-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="76079-138">El servicio `http.sys` combina el valor de la propiedad <xref:System.Uri.Host%2A?displayProperty=nameWithType> y la cadena en la línea de solicitud para crear un URI convertido.</span><span class="sxs-lookup"><span data-stu-id="76079-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="76079-139">Además, `http.sys` y la clase <xref:System.Uri?displayProperty=nameWithType> también hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="76079-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="76079-140">Quita la escape de todos los valores codificados por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="76079-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="76079-141">Convierte los caracteres que no son ASCII con codificación porcentual en una representación de caracteres UTF-16.</span><span class="sxs-lookup"><span data-stu-id="76079-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="76079-142">Tenga en cuenta que se admiten los caracteres UTF-8 y ANSI/DBCS, así como caracteres Unicode (codificación Unicode con el formato% uXXXX).</span><span class="sxs-lookup"><span data-stu-id="76079-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="76079-143">Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="76079-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="76079-144">Dado que la solicitud no contiene ninguna información sobre la codificación utilizada para los valores codificados con porcentaje, es posible que no sea posible determinar la codificación correcta solo mediante el análisis de los valores codificados por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="76079-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="76079-145">Por lo tanto `http.sys` proporciona dos claves del registro para modificar el proceso:</span><span class="sxs-lookup"><span data-stu-id="76079-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="76079-146">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="76079-146">Registry Key</span></span>|<span data-ttu-id="76079-147">Default Value</span><span class="sxs-lookup"><span data-stu-id="76079-147">Default Value</span></span>|<span data-ttu-id="76079-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="76079-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="76079-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="76079-149">EnableNonUTF8</span></span>|<span data-ttu-id="76079-150">1</span><span class="sxs-lookup"><span data-stu-id="76079-150">1</span></span>|<span data-ttu-id="76079-151">Si es cero, `http.sys` solo acepta direcciones URL con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="76079-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="76079-152">Si es distinto de cero, `http.sys` también acepta direcciones URL codificadas en ANSI o codificadas con DBCS en las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="76079-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="76079-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="76079-153">FavorUTF8</span></span>|<span data-ttu-id="76079-154">1</span><span class="sxs-lookup"><span data-stu-id="76079-154">1</span></span>|<span data-ttu-id="76079-155">Si es distinto de cero, `http.sys` siempre intenta descodificar primero una dirección URL como UTF-8. Si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, http. sys intenta descodificarlo como ANSI o DBCS.</span><span class="sxs-lookup"><span data-stu-id="76079-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="76079-156">Si cero (y EnableNonUTF8 es distinto de cero), `http.sys` intenta descodificarlo como ANSI o DBCS; Si no se realiza correctamente, intenta una conversión UTF-8.</span><span class="sxs-lookup"><span data-stu-id="76079-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="76079-157">Cuando <xref:System.Net.HttpListener> recibe una solicitud, utiliza el URI convertido de `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.</span><span class="sxs-lookup"><span data-stu-id="76079-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="76079-158">Hay una necesidad de admitir caracteres además de caracteres y números en los URI.</span><span class="sxs-lookup"><span data-stu-id="76079-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="76079-159">Un ejemplo es el URI siguiente, que se usa para recuperar información de cliente para el número de cliente "1/3812":</span><span class="sxs-lookup"><span data-stu-id="76079-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="76079-160">Observe la barra diagonal codificada en porcentaje en el URI (% 2F).</span><span class="sxs-lookup"><span data-stu-id="76079-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="76079-161">Esto es necesario, ya que en este caso el carácter de barra diagonal representa datos y no un delimitador de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="76079-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="76079-162">Al pasar la cadena al constructor URI se conducirá al URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="76079-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="76079-163">La división de la ruta de acceso en sus segmentos daría lugar a los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="76079-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="76079-164">No se trata de la intención del remitente de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="76079-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="76079-165">Si el atributo **unescapeRequestUrl** se establece en **false**, cuando el <xref:System.Net.HttpListener> recibe una solicitud, usa el URI sin formato en lugar del URI convertido de `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.</span><span class="sxs-lookup"><span data-stu-id="76079-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="76079-166">El valor predeterminado para el atributo **unescapeRequestUrl** es **true**.</span><span class="sxs-lookup"><span data-stu-id="76079-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="76079-167">La propiedad <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> se puede usar para obtener el valor actual del atributo **unescapeRequestUrl** de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="76079-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76079-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76079-168">Example</span></span>  
 <span data-ttu-id="76079-169">En el ejemplo siguiente se muestra cómo configurar la clase <xref:System.Net.HttpListener> cuando recibe una solicitud para usar el URI sin formato en lugar del URI convertido desde `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.</span><span class="sxs-lookup"><span data-stu-id="76079-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="76079-170">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="76079-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="76079-171">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="76079-171">Namespace</span></span>|<span data-ttu-id="76079-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="76079-172">System.Net</span></span>|  
|<span data-ttu-id="76079-173">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="76079-173">Schema Name</span></span>||  
|<span data-ttu-id="76079-174">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="76079-174">Validation File</span></span>||  
|<span data-ttu-id="76079-175">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="76079-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="76079-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="76079-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="76079-177">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="76079-177">Network Settings Schema</span></span>](index.md)
