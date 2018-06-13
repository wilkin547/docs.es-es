---
title: '&lt;httpListener&gt; Element (Network Settings)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a327f757f26c815d5b2cffe179af68bbe3d152eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744881"
---
# <a name="lthttplistenergt-element-network-settings"></a><span data-ttu-id="c33fe-102">&lt;httpListener&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="c33fe-102">&lt;httpListener&gt; Element (Network Settings)</span></span>
<span data-ttu-id="c33fe-103">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="c33fe-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
 <span data-ttu-id="c33fe-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c33fe-104">\<configuration></span></span>  
<span data-ttu-id="c33fe-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="c33fe-105">\<system.net></span></span>  
<span data-ttu-id="c33fe-106">\<Configuración ></span><span class="sxs-lookup"><span data-stu-id="c33fe-106">\<settings></span></span>  
<span data-ttu-id="c33fe-107">\<httpListener ></span><span class="sxs-lookup"><span data-stu-id="c33fe-107">\<httpListener></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33fe-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c33fe-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="c33fe-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="c33fe-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c33fe-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c33fe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c33fe-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c33fe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c33fe-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c33fe-112">Attributes</span></span>  
  
|<span data-ttu-id="c33fe-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c33fe-113">Attribute</span></span>|<span data-ttu-id="c33fe-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c33fe-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c33fe-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="c33fe-115">unescapeRequestUrl</span></span>|<span data-ttu-id="c33fe-116">Un valor booleano que indica si un <xref:System.Net.HttpListener> instancia utiliza el URI escape sin formato en lugar del URI convertido.</span><span class="sxs-lookup"><span data-stu-id="c33fe-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c33fe-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c33fe-117">Child Elements</span></span>  
 <span data-ttu-id="c33fe-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c33fe-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c33fe-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c33fe-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c33fe-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="c33fe-120">**Element**</span></span>|<span data-ttu-id="c33fe-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c33fe-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c33fe-122">Configuración</span><span class="sxs-lookup"><span data-stu-id="c33fe-122">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="c33fe-123">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c33fe-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c33fe-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c33fe-124">Remarks</span></span>  
 <span data-ttu-id="c33fe-125">El **unescapeRequestUrl** atributo indica si <xref:System.Net.HttpListener> utiliza el URI escape sin formato en lugar del URI convertido donde se convierten los valores codificados por porcentaje y se realizan otros pasos de normalización.</span><span class="sxs-lookup"><span data-stu-id="c33fe-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="c33fe-126">Cuando un <xref:System.Net.HttpListener> instancia recibe una solicitud a través de la `http.sys` servicio, crea una instancia de la cadena URI proporcionada por `http.sys`y lo expone como la <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c33fe-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="c33fe-127">El `http.sys` servicio expone dos cadenas URI de solicitud:</span><span class="sxs-lookup"><span data-stu-id="c33fe-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
-   <span data-ttu-id="c33fe-128">URI sin formato</span><span class="sxs-lookup"><span data-stu-id="c33fe-128">Raw URI</span></span>  
  
-   <span data-ttu-id="c33fe-129">URI convertido</span><span class="sxs-lookup"><span data-stu-id="c33fe-129">Converted URI</span></span>  
  
 <span data-ttu-id="c33fe-130">El URI sin formato es el <xref:System.Uri?displayProperty=nameWithType> proporcionado en la línea de solicitud de una solicitud HTTP:</span><span class="sxs-lookup"><span data-stu-id="c33fe-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="c33fe-131">El URI sin formato proporcionado por `http.sys` para la solicitud se ha mencionado anteriormente, es "/ path /".</span><span class="sxs-lookup"><span data-stu-id="c33fe-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="c33fe-132">Representa la cadena que sigue el verbo HTTP porque se envió a través de la red.</span><span class="sxs-lookup"><span data-stu-id="c33fe-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="c33fe-133">El `http.sys` servicio crea un URI convertido a partir de la información proporcionada en la solicitud usando el URI proporcionado en la línea de la solicitud HTTP y el encabezado de Host para determinar el servidor de origen de la solicitud se debería reenviar a.</span><span class="sxs-lookup"><span data-stu-id="c33fe-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="c33fe-134">Esto se realiza mediante la comparación de la información de la solicitud con un conjunto de prefijos URI registrados.</span><span class="sxs-lookup"><span data-stu-id="c33fe-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="c33fe-135">La documentación del SDK de servidor HTTP hace referencia a este URI convertido como la estructura HTTP_COOKED_URL.</span><span class="sxs-lookup"><span data-stu-id="c33fe-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="c33fe-136">Para poder comparar la solicitud con los prefijos URI registrados, necesita hacerse alguna normalización a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c33fe-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="c33fe-137">Para obtener el ejemplo encima del URI convertido sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="c33fe-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="c33fe-138">El `http.sys` servicio combina el <xref:System.Uri.Host%2A?displayProperty=nameWithType> valor de propiedad y la cadena en la línea de solicitud para crear un URI convertido.</span><span class="sxs-lookup"><span data-stu-id="c33fe-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="c33fe-139">Además, `http.sys` y <xref:System.Uri?displayProperty=nameWithType> clase también hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c33fe-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
-   <span data-ttu-id="c33fe-140">Quitar los caracteres de escape por ciento de todos los valores codificados.</span><span class="sxs-lookup"><span data-stu-id="c33fe-140">Un-escapes all percent encoded values.</span></span>  
  
-   <span data-ttu-id="c33fe-141">Caracteres no ASCII de codificación de porcentaje se convierte en una representación de caracteres UTF-16.</span><span class="sxs-lookup"><span data-stu-id="c33fe-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="c33fe-142">Tenga en cuenta que se admiten caracteres UTF-8 y ANSI/DBCS así como caracteres Unicode (codificación Unicode usando el formato % uXXXX).</span><span class="sxs-lookup"><span data-stu-id="c33fe-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
-   <span data-ttu-id="c33fe-143">Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c33fe-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="c33fe-144">Puesto que la solicitud no contiene toda la información sobre la codificación utilizada para los valores codificados por porcentaje, no sea posible determinar la codificación correcta simplemente analizando los valores codificados en porcentaje.</span><span class="sxs-lookup"><span data-stu-id="c33fe-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="c33fe-145">Por lo tanto, `http.sys` proporciona dos claves del registro para modificar el proceso:</span><span class="sxs-lookup"><span data-stu-id="c33fe-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="c33fe-146">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="c33fe-146">Registry Key</span></span>|<span data-ttu-id="c33fe-147">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c33fe-147">Default Value</span></span>|<span data-ttu-id="c33fe-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="c33fe-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="c33fe-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="c33fe-149">EnableNonUTF8</span></span>|<span data-ttu-id="c33fe-150">1</span><span class="sxs-lookup"><span data-stu-id="c33fe-150">1</span></span>|<span data-ttu-id="c33fe-151">Si es cero, `http.sys` acepta únicamente direcciones URL codificado en UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c33fe-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="c33fe-152">Si es distinto de cero, `http.sys` también acepta la codificación ANSI o DBCS codificado direcciones URL en las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="c33fe-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="c33fe-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="c33fe-153">FavorUTF8</span></span>|<span data-ttu-id="c33fe-154">1</span><span class="sxs-lookup"><span data-stu-id="c33fe-154">1</span></span>|<span data-ttu-id="c33fe-155">Si es distinto de cero, `http.sys` siempre intenta descodificar primero; una dirección URL como UTF-8 si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, Http.sys, a continuación, intenta descodificarlo como ANSI o DBCS.</span><span class="sxs-lookup"><span data-stu-id="c33fe-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="c33fe-156">Si es cero (y EnableNonUTF8 es distinto de cero), `http.sys` intenta descodificarlo como ANSI o DBCS; si no se realiza correctamente, trata de una conversión de UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c33fe-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="c33fe-157">Cuando <xref:System.Net.HttpListener> recibe una solicitud, usa el URI convertido de `http.sys` como entrada el <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c33fe-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="c33fe-158">Es necesario para admitir caracteres además de números y caracteres en identificadores URI.</span><span class="sxs-lookup"><span data-stu-id="c33fe-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="c33fe-159">Un ejemplo es el URI siguiente, que se usa para recuperar información del cliente para el cliente número "1/3812":</span><span class="sxs-lookup"><span data-stu-id="c33fe-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="c33fe-160">Tenga en cuenta la barra diagonal de codificación de porcentaje en el Uri (% 2F).</span><span class="sxs-lookup"><span data-stu-id="c33fe-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="c33fe-161">Esto es necesario, ya que en este caso el carácter de barra diagonal representa los datos y no un delimitador de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c33fe-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="c33fe-162">Pase la cadena al constructor Uri conducirá al URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="c33fe-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="c33fe-163">Dividir la ruta de acceso en sus segmentos, se crearán los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c33fe-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="c33fe-164">Esto no es la intención del remitente de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c33fe-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="c33fe-165">Si el **unescapeRequestUrl** atributo está establecido en **false**, a continuación cuando la <xref:System.Net.HttpListener> recibe una solicitud, usa el URI sin formato en lugar del URI convertido de `http.sys` como entrada para el <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c33fe-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="c33fe-166">El valor predeterminado para la **unescapeRequestUrl** atributo es **true**.</span><span class="sxs-lookup"><span data-stu-id="c33fe-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="c33fe-167">El <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> propiedad puede utilizarse para obtener el valor actual de la **unescapeRequestUrl** atributos de archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="c33fe-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c33fe-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c33fe-168">Example</span></span>  
 <span data-ttu-id="c33fe-169">En el ejemplo siguiente se muestra cómo configurar el <xref:System.Net.HttpListener> clase cuando se recibe una solicitud para usar el URI sin formato en lugar del URI convertido de `http.sys` como entrada el <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c33fe-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="c33fe-170">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="c33fe-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="c33fe-171">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c33fe-171">Namespace</span></span>|<span data-ttu-id="c33fe-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="c33fe-172">System.Net</span></span>|  
|<span data-ttu-id="c33fe-173">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="c33fe-173">Schema Name</span></span>||  
|<span data-ttu-id="c33fe-174">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="c33fe-174">Validation File</span></span>||  
|<span data-ttu-id="c33fe-175">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="c33fe-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="c33fe-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="c33fe-176">See Also</span></span>  
 <xref:System.Net.Configuration.HttpListenerElement>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpListenerRequest.Url%2A>  
 [<span data-ttu-id="c33fe-177">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c33fe-177">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
