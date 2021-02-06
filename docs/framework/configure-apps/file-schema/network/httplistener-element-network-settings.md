---
description: 'Más información acerca de: <httpListener> elemento (configuración de red)'
title: Elemento <httpListener> (configuración de red)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 18c139ad7767370ecd3a4116e352b7614914d199
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652866"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="74e04-103">Elemento \<httpListener> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="74e04-103">\<httpListener> Element (Network Settings)</span></span>

<span data-ttu-id="74e04-104">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="74e04-104">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**

## <a name="syntax"></a><span data-ttu-id="74e04-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74e04-105">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="74e04-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="74e04-106">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74e04-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="74e04-107">Attributes and Elements</span></span>  

 <span data-ttu-id="74e04-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="74e04-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74e04-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="74e04-109">Attributes</span></span>  
  
|<span data-ttu-id="74e04-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="74e04-110">Attribute</span></span>|<span data-ttu-id="74e04-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="74e04-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74e04-112">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="74e04-112">unescapeRequestUrl</span></span>|<span data-ttu-id="74e04-113">Valor booleano que indica si una <xref:System.Net.HttpListener> instancia de usa el URI sin escape sin formato en lugar del URI convertido.</span><span class="sxs-lookup"><span data-stu-id="74e04-113">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74e04-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="74e04-114">Child Elements</span></span>  

 <span data-ttu-id="74e04-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74e04-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74e04-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="74e04-116">Parent Elements</span></span>  
  
|<span data-ttu-id="74e04-117">**Element**</span><span class="sxs-lookup"><span data-stu-id="74e04-117">**Element**</span></span>|<span data-ttu-id="74e04-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="74e04-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="74e04-119">settings</span><span class="sxs-lookup"><span data-stu-id="74e04-119">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="74e04-120">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="74e04-120">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74e04-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74e04-121">Remarks</span></span>  

 <span data-ttu-id="74e04-122">El atributo **unescapeRequestUrl** indica si <xref:System.Net.HttpListener> usa el URI sin escape sin formato en lugar del URI convertido en el que se convierten los valores con codificación porcentual y se toman otros pasos de normalización.</span><span class="sxs-lookup"><span data-stu-id="74e04-122">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="74e04-123">Cuando una <xref:System.Net.HttpListener> instancia recibe una solicitud a través del `http.sys` servicio, crea una instancia de la cadena URI proporcionada por `http.sys` y la expone como la <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="74e04-123">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="74e04-124">El `http.sys` servicio expone dos cadenas URI de solicitud:</span><span class="sxs-lookup"><span data-stu-id="74e04-124">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="74e04-125">URI sin formato</span><span class="sxs-lookup"><span data-stu-id="74e04-125">Raw URI</span></span>  
  
- <span data-ttu-id="74e04-126">URI convertido</span><span class="sxs-lookup"><span data-stu-id="74e04-126">Converted URI</span></span>  
  
 <span data-ttu-id="74e04-127">El URI sin formato es el <xref:System.Uri?displayProperty=nameWithType> proporcionado en la línea de solicitud de una solicitud http:</span><span class="sxs-lookup"><span data-stu-id="74e04-127">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="74e04-128">El URI sin formato proporcionado por `http.sys` para la solicitud mencionada anteriormente es "/path/".</span><span class="sxs-lookup"><span data-stu-id="74e04-128">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="74e04-129">Representa la cadena que sigue al verbo HTTP tal como se envió a través de la red.</span><span class="sxs-lookup"><span data-stu-id="74e04-129">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="74e04-130">El `http.sys` servicio crea un URI convertido a partir de la información proporcionada en la solicitud mediante el URI proporcionado en la línea de solicitud HTTP y el encabezado de host para determinar el servidor de origen al que se debe reenviar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="74e04-130">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="74e04-131">Para ello, se compara la información de la solicitud con un conjunto de prefijos de URI registrados.</span><span class="sxs-lookup"><span data-stu-id="74e04-131">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="74e04-132">La documentación del SDK del servidor HTTP hace referencia a este URI convertido como la estructura HTTP_COOKED_URL.</span><span class="sxs-lookup"><span data-stu-id="74e04-132">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="74e04-133">Para poder comparar la solicitud con prefijos URI registrados, es necesario realizar alguna normalización a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="74e04-133">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="74e04-134">Para el ejemplo anterior, el URI convertido sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="74e04-134">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="74e04-135">El `http.sys` servicio combina el <xref:System.Uri.Host%2A?displayProperty=nameWithType> valor de propiedad y la cadena en la línea de solicitud para crear un URI convertido.</span><span class="sxs-lookup"><span data-stu-id="74e04-135">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="74e04-136">Además, `http.sys` la <xref:System.Uri?displayProperty=nameWithType> clase también hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="74e04-136">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="74e04-137">Quita la escape de todos los valores codificados por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="74e04-137">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="74e04-138">Convierte los caracteres que no son ASCII con codificación porcentual en una representación de caracteres UTF-16.</span><span class="sxs-lookup"><span data-stu-id="74e04-138">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="74e04-139">Tenga en cuenta que se admiten los caracteres UTF-8 y ANSI/DBCS, así como caracteres Unicode (codificación Unicode con el formato% uXXXX).</span><span class="sxs-lookup"><span data-stu-id="74e04-139">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="74e04-140">Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="74e04-140">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="74e04-141">Dado que la solicitud no contiene ninguna información sobre la codificación utilizada para los valores codificados con porcentaje, es posible que no sea posible determinar la codificación correcta solo mediante el análisis de los valores codificados por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="74e04-141">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="74e04-142">Por lo tanto, `http.sys` proporciona dos claves del registro para modificar el proceso:</span><span class="sxs-lookup"><span data-stu-id="74e04-142">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="74e04-143">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="74e04-143">Registry Key</span></span>|<span data-ttu-id="74e04-144">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="74e04-144">Default Value</span></span>|<span data-ttu-id="74e04-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="74e04-145">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="74e04-146">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="74e04-146">EnableNonUTF8</span></span>|<span data-ttu-id="74e04-147">1</span><span class="sxs-lookup"><span data-stu-id="74e04-147">1</span></span>|<span data-ttu-id="74e04-148">Si es cero, `http.sys` solo acepta direcciones URL con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="74e04-148">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="74e04-149">Si es distinto de cero, `http.sys` también acepta direcciones URL codificadas en ANSI o codificadas con DBCS en las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="74e04-149">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="74e04-150">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="74e04-150">FavorUTF8</span></span>|<span data-ttu-id="74e04-151">1</span><span class="sxs-lookup"><span data-stu-id="74e04-151">1</span></span>|<span data-ttu-id="74e04-152">Si es distinto de cero, `http.sys` siempre intenta descodificar una dirección URL como UTF-8 primero; si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, Http.sys intenta descodificarlo como ANSI o DBCS.</span><span class="sxs-lookup"><span data-stu-id="74e04-152">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="74e04-153">Si cero (y EnableNonUTF8 es distinto de cero), `http.sys` intenta descodificarlo como ANSI o DBCS; si no se realiza correctamente, intenta una conversión UTF-8.</span><span class="sxs-lookup"><span data-stu-id="74e04-153">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="74e04-154">Cuando <xref:System.Net.HttpListener> recibe una solicitud, utiliza el URI convertido de `http.sys` como entrada para la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="74e04-154">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="74e04-155">Hay una necesidad de admitir caracteres además de caracteres y números en los URI.</span><span class="sxs-lookup"><span data-stu-id="74e04-155">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="74e04-156">Un ejemplo es el URI siguiente, que se usa para recuperar información de cliente para el número de cliente "1/3812":</span><span class="sxs-lookup"><span data-stu-id="74e04-156">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="74e04-157">Observe la barra diagonal codificada en porcentaje en el URI (% 2F).</span><span class="sxs-lookup"><span data-stu-id="74e04-157">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="74e04-158">Esto es necesario, ya que en este caso el carácter de barra diagonal representa datos y no un delimitador de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="74e04-158">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="74e04-159">Al pasar la cadena al constructor URI se conducirá al URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="74e04-159">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="74e04-160">La división de la ruta de acceso en sus segmentos daría lugar a los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="74e04-160">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="74e04-161">No se trata de la intención del remitente de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="74e04-161">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="74e04-162">Si el atributo **unescapeRequestUrl** se establece en **false**, cuando <xref:System.Net.HttpListener> recibe una solicitud, usa el URI sin formato en lugar del URI convertido desde `http.sys` como entrada a la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="74e04-162">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="74e04-163">El valor predeterminado para el atributo **unescapeRequestUrl** es **true**.</span><span class="sxs-lookup"><span data-stu-id="74e04-163">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="74e04-164">La <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> propiedad se puede utilizar para obtener el valor actual del atributo **unescapeRequestUrl** de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="74e04-164">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74e04-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74e04-165">Example</span></span>  

 <span data-ttu-id="74e04-166">En el ejemplo siguiente se muestra cómo configurar la <xref:System.Net.HttpListener> clase cuando recibe una solicitud para usar el URI sin formato en lugar del URI convertido desde `http.sys` como entrada a la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="74e04-166">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="74e04-167">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="74e04-167">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="74e04-168">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="74e04-168">Namespace</span></span>|<span data-ttu-id="74e04-169">System.Net</span><span class="sxs-lookup"><span data-stu-id="74e04-169">System.Net</span></span>|  
|<span data-ttu-id="74e04-170">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="74e04-170">Schema Name</span></span>||  
|<span data-ttu-id="74e04-171">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="74e04-171">Validation File</span></span>||  
|<span data-ttu-id="74e04-172">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="74e04-172">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="74e04-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="74e04-173">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="74e04-174">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="74e04-174">Network Settings Schema</span></span>](index.md)
