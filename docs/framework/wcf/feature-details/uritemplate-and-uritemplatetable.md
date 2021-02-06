---
description: 'Más información acerca de: UriTemplate y UriTemplateTable'
title: UriTemplate y UriTemplateTable
ms.date: 03/30/2017
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
ms.openlocfilehash: 7abcf0125108e4f48e392e8bb817dda77dfedd38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632417"
---
# <a name="uritemplate-and-uritemplatetable"></a><span data-ttu-id="3feaf-103">UriTemplate y UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="3feaf-103">UriTemplate and UriTemplateTable</span></span>

<span data-ttu-id="3feaf-104">Los desarrolladores web necesitan poder describir la forma y el diseño de los URI a los que sus servicios responden.</span><span class="sxs-lookup"><span data-stu-id="3feaf-104">Web developers require the ability to describe the shape and layout of the URIs that their services respond to.</span></span> <span data-ttu-id="3feaf-105">Windows Communication Foundation (WCF) agrega dos clases nuevas para ofrecer a los desarrolladores el control sobre sus URI.</span><span class="sxs-lookup"><span data-stu-id="3feaf-105">Windows Communication Foundation (WCF) added two new classes to give developers control over their URIs.</span></span> <span data-ttu-id="3feaf-106"><xref:System.UriTemplate> y <xref:System.UriTemplateTable> forman la base del motor de distribución basado en URI en WCF.</span><span class="sxs-lookup"><span data-stu-id="3feaf-106"><xref:System.UriTemplate> and <xref:System.UriTemplateTable> form the basis of the URI-based dispatch engine in WCF.</span></span> <span data-ttu-id="3feaf-107">Estas clases también se pueden utilizar por sí mismas, lo que permite a los desarrolladores aprovechar las plantillas y el mecanismo de asignación de URI sin necesidad de implementar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="3feaf-107">These classes can also be used on their own, allowing developers to take advantage of templates and the URI mapping mechanism without implementing a WCF service.</span></span>  
  
## <a name="templates"></a><span data-ttu-id="3feaf-108">Plantillas</span><span class="sxs-lookup"><span data-stu-id="3feaf-108">Templates</span></span>  

 <span data-ttu-id="3feaf-109">Una plantilla es una manera de describir un conjunto de URI relativos.</span><span class="sxs-lookup"><span data-stu-id="3feaf-109">A template is a way to describe a set of relative URIs.</span></span> <span data-ttu-id="3feaf-110">El conjunto de plantillas URI de la tabla siguiente muestra cómo se podría definir un sistema que recupera varios tipos de información meteorológica.</span><span class="sxs-lookup"><span data-stu-id="3feaf-110">The set of URI templates in the following table shows how a system that retrieves various types of weather information might be defined.</span></span>  
  
|<span data-ttu-id="3feaf-111">data</span><span class="sxs-lookup"><span data-stu-id="3feaf-111">Data</span></span>|<span data-ttu-id="3feaf-112">Plantilla</span><span class="sxs-lookup"><span data-stu-id="3feaf-112">Template</span></span>|  
|----------|--------------|  
|<span data-ttu-id="3feaf-113">Previsión nacional</span><span class="sxs-lookup"><span data-stu-id="3feaf-113">National Forecast</span></span>|<span data-ttu-id="3feaf-114">tiempo/nacional</span><span class="sxs-lookup"><span data-stu-id="3feaf-114">weather/national</span></span>|  
|<span data-ttu-id="3feaf-115">Previsión estatal</span><span class="sxs-lookup"><span data-stu-id="3feaf-115">State Forecast</span></span>|<span data-ttu-id="3feaf-116">tiempo/{estado}</span><span class="sxs-lookup"><span data-stu-id="3feaf-116">weather/{state}</span></span>|  
|<span data-ttu-id="3feaf-117">Previsión de la ciudad</span><span class="sxs-lookup"><span data-stu-id="3feaf-117">City Forecast</span></span>|<span data-ttu-id="3feaf-118">tiempo/{estado}/{ciudad}</span><span class="sxs-lookup"><span data-stu-id="3feaf-118">weather/{state}/{city}</span></span>|  
|<span data-ttu-id="3feaf-119">Previsión de Actividad</span><span class="sxs-lookup"><span data-stu-id="3feaf-119">Activity Forecast</span></span>|<span data-ttu-id="3feaf-120">tiempo/{estado}/{ciudad}/{actividad}</span><span class="sxs-lookup"><span data-stu-id="3feaf-120">weather/{state}/{city}/{activity}</span></span>|  
  
 <span data-ttu-id="3feaf-121">Esta tabla describe un conjunto de URI estructuralmente similares.</span><span class="sxs-lookup"><span data-stu-id="3feaf-121">This table describes a set of structurally similar URIs.</span></span> <span data-ttu-id="3feaf-122">Cada entrada es una plantilla URI.</span><span class="sxs-lookup"><span data-stu-id="3feaf-122">Each entry is a URI template.</span></span> <span data-ttu-id="3feaf-123">Los segmentos entre llaves describen las variables.</span><span class="sxs-lookup"><span data-stu-id="3feaf-123">The segments in curly braces describe variables.</span></span> <span data-ttu-id="3feaf-124">Los segmentos que no están entre llaves describen cadenas literales.</span><span class="sxs-lookup"><span data-stu-id="3feaf-124">The segments not in curly braces describe literal strings.</span></span> <span data-ttu-id="3feaf-125">Las clases de plantilla de WCF permiten a un desarrollador tomar un URI de entrada, por ejemplo, "/Weather/wa/Seattle/Cycling", y hacer que coincida con una plantilla que lo describe, "/Weather/{State}/{City}/{Activity}".</span><span class="sxs-lookup"><span data-stu-id="3feaf-125">The WCF template classes allow a developer to take an incoming URI, for example, "/weather/wa/seattle/cycling", and match it to a template that describes it, "/weather/{state}/{city}/{activity}".</span></span>  
  
## <a name="uritemplate"></a><span data-ttu-id="3feaf-126">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="3feaf-126">UriTemplate</span></span>  

 <span data-ttu-id="3feaf-127"><xref:System.UriTemplate> es una clase que encapsula una plantilla URI.</span><span class="sxs-lookup"><span data-stu-id="3feaf-127"><xref:System.UriTemplate> is a class that encapsulates a URI template.</span></span> <span data-ttu-id="3feaf-128">El constructor toma un parámetro de cadena que define la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-128">The constructor takes a string parameter that defines the template.</span></span> <span data-ttu-id="3feaf-129">Esta cadena contiene la plantilla en el formato descrito en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3feaf-129">This string contains the template in the format described in the next section.</span></span> <span data-ttu-id="3feaf-130">La clase <xref:System.UriTemplate> proporciona métodos que le permiten igualar un URI de entrada a una plantilla, generar un URI a partir de una plantilla, recuperar una colección de nombres de variables usadas en la plantilla, determinar si dos plantillas son equivalentes, y devolver la cadena de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-130">The <xref:System.UriTemplate> class provides methods that allow you match an incoming URI to a template, generate a URI from a template, retrieve a collection of variable names used in the template, determine whether two templates are equivalent, and return the template's string.</span></span>  
  
 <span data-ttu-id="3feaf-131"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> toma una dirección base y un candidato a identificador URI e intenta asociar el URI a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-131"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> takes a base address and a candidate URI and attempts to match the URI to the template.</span></span> <span data-ttu-id="3feaf-132">Si la coincidencia se realiza correctamente, se devuelve una instancia <xref:System.UriTemplateMatch>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-132">If the match is successful, a <xref:System.UriTemplateMatch> instance is returned.</span></span> <span data-ttu-id="3feaf-133">El objeto <xref:System.UriTemplateMatch> contiene una dirección URI base, el URI candidato, una colección de nombres/valores de los parámetros de consulta, una matriz de segmentos de ruta de acceso relativa, una colección de nombres/valores de variables comparadas, la instancia de <xref:System.UriTemplate> utilizada para la comparación, una cadena que contiene cualquier parte no coincidente del URI candidato (se usa cuando la plantilla tiene un carácter comodín) y un objeto que está asociado a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-133">The <xref:System.UriTemplateMatch> object contains a base URI, the candidate URI, a name/value collection of the query parameters, an array of the relative path segments, a name/value collection of variables that were matched, the <xref:System.UriTemplate> instance used to perform the match, a string that contains any unmatched portion of the candidate URI (used when the template has a wildcard), and an object that is associated with the template.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3feaf-134">La clase <xref:System.UriTemplate> omite el esquema y número de puerto al comparar un URI candidato con una plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-134">The <xref:System.UriTemplate> class ignores the scheme and port number when matching a candidate URI to a template.</span></span>  
  
 <span data-ttu-id="3feaf-135">Hay dos métodos que le permiten generar un URI a partir de una plantilla: <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> y <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-135">There are two methods that allow you to generate a URI from a template, <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> and <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span></span> <span data-ttu-id="3feaf-136"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> toma una dirección base y una colección de nombre y valor de parámetros.</span><span class="sxs-lookup"><span data-stu-id="3feaf-136"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> takes a base address and a name/value collection of parameters.</span></span> <span data-ttu-id="3feaf-137">Estos parámetros se sustituyen por variables cuando se enlaza la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-137">These parameters are substituted for variables when the template is bound.</span></span> <span data-ttu-id="3feaf-138"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> toma los pares de nombre/valor y los sustituye de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="3feaf-138"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> takes the name/value pairs and substitutes them left to right.</span></span>  
  
 <span data-ttu-id="3feaf-139"><xref:System.UriTemplate.ToString> devuelve la cadena de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-139"><xref:System.UriTemplate.ToString> returns the template string.</span></span>  
  
 <span data-ttu-id="3feaf-140">La propiedad <xref:System.UriTemplate.PathSegmentVariableNames%2A> contiene una colección de los nombres de las variables usadas dentro de segmentos de ruta de acceso en la cadena de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-140">The <xref:System.UriTemplate.PathSegmentVariableNames%2A> property contains a collection of the names of the variables used within path segments in the template string.</span></span>  
  
 <span data-ttu-id="3feaf-141"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> toma <xref:System.UriTemplate> como parámetro y devuelve un valor booleano que especifica si las dos plantillas son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="3feaf-141"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> takes a <xref:System.UriTemplate> as a parameter and returns a Boolean value that specifies whether the two templates are equivalent.</span></span> <span data-ttu-id="3feaf-142">Para obtener más información, vea la sección equivalencia de plantillas más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="3feaf-142">For more information, see the Template Equivalence section later in this topic.</span></span>  
  
 <span data-ttu-id="3feaf-143"><xref:System.UriTemplate> está diseñado para funcionar con cualquier esquema de URI que cumpla la gramática de URI de HTTP.</span><span class="sxs-lookup"><span data-stu-id="3feaf-143"><xref:System.UriTemplate> is designed to work with any URI scheme that conforms to the HTTP URI grammar.</span></span> <span data-ttu-id="3feaf-144">A continuación se ofrecen ejemplos de esquemas de URI compatibles.</span><span class="sxs-lookup"><span data-stu-id="3feaf-144">The following are examples of supported URI schemes.</span></span>  
  
- `http://`  
  
- `https://`  
  
- `net.tcp://`  
  
- `net.pipe://`  
  
- `sb://`  
  
 <span data-ttu-id="3feaf-145">Esquemas como file:// y urn:// no cumplen la gramática de URI de HTTP y producen resultados imprevisibles cuando se usan con plantillas URI.</span><span class="sxs-lookup"><span data-stu-id="3feaf-145">Schemes like file:// and urn:// do not conform to the HTTP URI grammar and cause unpredictable results when used with URI templates.</span></span>  
  
### <a name="template-string-syntax"></a><span data-ttu-id="3feaf-146">Sintaxis de cadenas de plantillas</span><span class="sxs-lookup"><span data-stu-id="3feaf-146">Template String Syntax</span></span>  

 <span data-ttu-id="3feaf-147">Una plantilla tiene tres partes: una ruta de acceso, una consulta opcional y un fragmento opcional.</span><span class="sxs-lookup"><span data-stu-id="3feaf-147">A template has three parts: a path, an optional query, and an optional fragment.</span></span> <span data-ttu-id="3feaf-148">Para obtener un ejemplo, vea la plantilla siguiente:</span><span class="sxs-lookup"><span data-stu-id="3feaf-148">For an example, see the following template:</span></span>  
  
`"/weather/{state}/{city}?forecast={length)#frag1`  
  
 <span data-ttu-id="3feaf-149">La ruta de acceso consiste de "/tiempo/{estado}/{ciudad}", la consulta consiste de"? previsión={longitud} y el fragmento consiste de "#frag1."</span><span class="sxs-lookup"><span data-stu-id="3feaf-149">The path consists of "/weather/{state}/{city}", the query consists of "?forecast={length}, and the fragment consists of "#frag1".</span></span>  
  
 <span data-ttu-id="3feaf-150">Las barras diagonales iniciales y finales son opcionales en la expresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3feaf-150">Leading and trailing slashes are optional in the path expression.</span></span> <span data-ttu-id="3feaf-151">Se pueden omitir completamente las expresiones de consulta y fragmento.</span><span class="sxs-lookup"><span data-stu-id="3feaf-151">Both the query and fragment expressions can be omitted entirely.</span></span> <span data-ttu-id="3feaf-152">Una ruta de acceso consta de una serie de segmentos delimitados por '/', cada segmento puede tener un valor literal, un nombre de variable (escrito en {llaves}) o un carácter comodín (escrito como ' \* ').</span><span class="sxs-lookup"><span data-stu-id="3feaf-152">A path consists of a series of segments delimited by '/', each segment can have a literal value, a variable name (written in {curly braces}), or a wildcard (written as '\*').</span></span> <span data-ttu-id="3feaf-153">En la plantilla anterior el segmento “\tiempo\” es un valor literal mientras que “{estado}” y “{ciudad}” son las variables.</span><span class="sxs-lookup"><span data-stu-id="3feaf-153">In the previous template the "\weather\ segment is a literal value while "{state}" and "{city}" are variables.</span></span> <span data-ttu-id="3feaf-154">Las variables toman el nombre del contenido de sus llaves y, posteriormente, se pueden reemplazar por un valor concreto para crear un *URI cerrado*.</span><span class="sxs-lookup"><span data-stu-id="3feaf-154">Variables take their name from the contents of their curly braces and they can later be replaced with a concrete value to create a *closed URI*.</span></span> <span data-ttu-id="3feaf-155">El carácter comodín es opcional, pero solo puede aparecer al final del URI, donde coincide lógicamente con "el resto de la ruta de acceso".</span><span class="sxs-lookup"><span data-stu-id="3feaf-155">The wildcard is optional, but can only appear at the end of the URI, where it logically matches "the rest of the path".</span></span>  
  
 <span data-ttu-id="3feaf-156">La expresión de consulta, si está presente, especifica una serie de pares de nombre/valor desordenados delimitados por ' & '.</span><span class="sxs-lookup"><span data-stu-id="3feaf-156">The query expression, if present, specifies a series of unordered name/value pairs delimited by '&'.</span></span> <span data-ttu-id="3feaf-157">Los elementos de la expresión de consulta pueden ser pares literales (x=2) o un par de variables (x = {var}).</span><span class="sxs-lookup"><span data-stu-id="3feaf-157">Elements of the query expression can either be literal pairs (x=2) or a variable pair (x={var}).</span></span> <span data-ttu-id="3feaf-158">Solo el lado derecho de la consulta puede tener una expresión variable.</span><span class="sxs-lookup"><span data-stu-id="3feaf-158">Only the right side of the query can have a variable expression.</span></span> <span data-ttu-id="3feaf-159">({someName} = {someValue} no está permitido.</span><span class="sxs-lookup"><span data-stu-id="3feaf-159">({someName} = {someValue} is not allowed.</span></span> <span data-ttu-id="3feaf-160">No se permiten los valores no emparejados (? x).</span><span class="sxs-lookup"><span data-stu-id="3feaf-160">Unpaired values (?x) are not permitted.</span></span> <span data-ttu-id="3feaf-161">No hay ninguna diferencia entre una expresión de consulta vacía y una expresión de consulta compuesta de un único '?' (ambos significan “cualquier consulta”).</span><span class="sxs-lookup"><span data-stu-id="3feaf-161">There is no difference between an empty query expression and a query expression consisting of just a single '?' (both mean "any query").</span></span>  
  
 <span data-ttu-id="3feaf-162">La expresión de fragmento puede estar compuesta de un valor literal; no se permiten variables.</span><span class="sxs-lookup"><span data-stu-id="3feaf-162">The fragment expression can consist of a literal value, no variables are allowed.</span></span>  
  
 <span data-ttu-id="3feaf-163">Todos los nombres de variables de la plantilla dentro de una cadena de la plantilla deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="3feaf-163">All template variable names within a template string must be unique.</span></span> <span data-ttu-id="3feaf-164">Los nombres de variables de la plantilla no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-164">Template variable names are case-insensitive.</span></span>  
  
 <span data-ttu-id="3feaf-165">Ejemplos de cadenas de plantillas válidas:</span><span class="sxs-lookup"><span data-stu-id="3feaf-165">Examples of valid template strings:</span></span>  
  
- <span data-ttu-id="3feaf-166">""</span><span class="sxs-lookup"><span data-stu-id="3feaf-166">""</span></span>  
  
- <span data-ttu-id="3feaf-167">"/zapato"</span><span class="sxs-lookup"><span data-stu-id="3feaf-167">"/shoe"</span></span>  
  
- <span data-ttu-id="3feaf-168">"/Shoe/ \* "</span><span class="sxs-lookup"><span data-stu-id="3feaf-168">"/shoe/\*"</span></span>  
  
- <span data-ttu-id="3feaf-169">"{zapato}/barco"</span><span class="sxs-lookup"><span data-stu-id="3feaf-169">"{shoe}/boat"</span></span>  
  
- <span data-ttu-id="3feaf-170">"{zapatos}/{Boat}/Bed/{quilt}"</span><span class="sxs-lookup"><span data-stu-id="3feaf-170">"{shoe}/{boat}/bed/{quilt}"</span></span>  
  
- <span data-ttu-id="3feaf-171">"zapatos/{barco}"</span><span class="sxs-lookup"><span data-stu-id="3feaf-171">"shoe/{boat}"</span></span>  
  
- <span data-ttu-id="3feaf-172">"zapatos/{barco}/ \* "</span><span class="sxs-lookup"><span data-stu-id="3feaf-172">"shoe/{boat}/\*"</span></span>  
  
- <span data-ttu-id="3feaf-173">"zapatos/barco? x = 2"</span><span class="sxs-lookup"><span data-stu-id="3feaf-173">"shoe/boat?x=2"</span></span>  
  
- <span data-ttu-id="3feaf-174">"zapatos/{barco}? x = {cama}"</span><span class="sxs-lookup"><span data-stu-id="3feaf-174">"shoe/{boat}?x={bed}"</span></span>  
  
- <span data-ttu-id="3feaf-175">"zapatos/{barco}? x = {cama} &y = banda"</span><span class="sxs-lookup"><span data-stu-id="3feaf-175">"shoe/{boat}?x={bed}&y=band"</span></span>  
  
- <span data-ttu-id="3feaf-176">"? x = {zapatos}"</span><span class="sxs-lookup"><span data-stu-id="3feaf-176">"?x={shoe}"</span></span>  
  
- <span data-ttu-id="3feaf-177">"zapatos? x = 3&y = {var}</span><span class="sxs-lookup"><span data-stu-id="3feaf-177">"shoe?x=3&y={var}</span></span>  
  
 <span data-ttu-id="3feaf-178">Ejemplos de cadenas de plantillas no válidas:</span><span class="sxs-lookup"><span data-stu-id="3feaf-178">Examples of invalid template strings:</span></span>  
  
- <span data-ttu-id="3feaf-179">"{zapatos}/{SHOE}/x = 2": nombres de variables duplicados.</span><span class="sxs-lookup"><span data-stu-id="3feaf-179">"{shoe}/{SHOE}/x=2" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="3feaf-180">"{zapatos}/Boat/? cama = {zapatos}": nombres de variables duplicados.</span><span class="sxs-lookup"><span data-stu-id="3feaf-180">"{shoe}/boat/?bed={shoe}" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="3feaf-181">"? x = 2&x = 3": los pares de nombre y valor dentro de una cadena de consulta deben ser únicos, aunque sean literales.</span><span class="sxs-lookup"><span data-stu-id="3feaf-181">"?x=2&x=3" – Name/value pairs within a query string must be unique, even if they are literals.</span></span>  
  
- <span data-ttu-id="3feaf-182">"? x = 2&": la cadena de consulta tiene un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="3feaf-182">"?x=2&" – Query string is malformed.</span></span>  
  
- <span data-ttu-id="3feaf-183">"? 2&x = {zapatos}": la cadena de consulta debe ser un par de nombre y valor.</span><span class="sxs-lookup"><span data-stu-id="3feaf-183">"?2&x={shoe}" – Query string must be name/value pairs.</span></span>  
  
- <span data-ttu-id="3feaf-184">"? y = 2&&X = 3": la cadena de consulta debe ser pares nombre-valor, los nombres no pueden comenzar por "&".</span><span class="sxs-lookup"><span data-stu-id="3feaf-184">"?y=2&&X=3" – Query string must be name value pairs, names cannot start with '&'.</span></span>  
  
### <a name="compound-path-segments"></a><span data-ttu-id="3feaf-185">Segmentos de ruta de acceso compuestos</span><span class="sxs-lookup"><span data-stu-id="3feaf-185">Compound Path Segments</span></span>  

 <span data-ttu-id="3feaf-186">Los segmentos de ruta de acceso compuestos permiten que un solo segmento de ruta de acceso de URI contenga varias variables y variables combinadas con literales.</span><span class="sxs-lookup"><span data-stu-id="3feaf-186">Compound path segments allow a single URI path segment to contain multiple variables as well as variables combined with literals.</span></span> <span data-ttu-id="3feaf-187">A continuación, se ofrecen ejemplos de segmentos de ruta de acceso compuestos válidos.</span><span class="sxs-lookup"><span data-stu-id="3feaf-187">The following are examples of valid compound path segments.</span></span>  
  
- <span data-ttu-id="3feaf-188">/nombreDeArchivo.{ext}/</span><span class="sxs-lookup"><span data-stu-id="3feaf-188">/filename.{ext}/</span></span>  
  
- <span data-ttu-id="3feaf-189">/{nombreDeArchivo}.jpg/</span><span class="sxs-lookup"><span data-stu-id="3feaf-189">/{filename}.jpg/</span></span>  
  
- <span data-ttu-id="3feaf-190">/{nombreDeArchivo}.{ext}/</span><span class="sxs-lookup"><span data-stu-id="3feaf-190">/{filename}.{ext}/</span></span>  
  
- <span data-ttu-id="3feaf-191">/{a}.{b}algúnLiteral{c}({d})/</span><span class="sxs-lookup"><span data-stu-id="3feaf-191">/{a}.{b}someLiteral{c}({d})/</span></span>  
  
 <span data-ttu-id="3feaf-192">A continuación, se ofrecen ejemplos de segmentos de ruta de acceso no válidos.</span><span class="sxs-lookup"><span data-stu-id="3feaf-192">The following are examples of invalid path segments.</span></span>  
  
- <span data-ttu-id="3feaf-193">{}Las variables/-deben tener nombre.</span><span class="sxs-lookup"><span data-stu-id="3feaf-193">/{} - Variables must be named.</span></span>  
  
- <span data-ttu-id="3feaf-194">/{zapato}{barco}: las variables deben estar separadas por un literal.</span><span class="sxs-lookup"><span data-stu-id="3feaf-194">/{shoe}{boat} - Variables must be separated by a literal.</span></span>  
  
### <a name="matching-and-compound-path-segments"></a><span data-ttu-id="3feaf-195">Segmentos de ruta de acceso coincidentes y compuestos</span><span class="sxs-lookup"><span data-stu-id="3feaf-195">Matching and Compound Path Segments</span></span>  

 <span data-ttu-id="3feaf-196">Los segmentos de ruta de acceso permiten definir un UriTemplate que tenga varias variables en un solo segmento de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3feaf-196">Compound path segments allow you to define a UriTemplate that has multiple variables within a single path segment.</span></span> <span data-ttu-id="3feaf-197">Por ejemplo, en la siguiente cadena de plantilla: "Addresses/{State}. {City} "se definen dos variables (State y City) dentro del mismo segmento.</span><span class="sxs-lookup"><span data-stu-id="3feaf-197">For example, in the following template string: "Addresses/{state}.{city}" two variables (state and city) are defined within the same segment.</span></span> <span data-ttu-id="3feaf-198">Esta plantilla coincidiría con una dirección URL como, `http://example.com/Washington.Redmond` pero también coincidirá con una dirección URL como `http://example.com/Washington.Redmond.Microsoft` .</span><span class="sxs-lookup"><span data-stu-id="3feaf-198">This template would match a URL such as `http://example.com/Washington.Redmond` but it will also match an URL like `http://example.com/Washington.Redmond.Microsoft`.</span></span> <span data-ttu-id="3feaf-199">En el último caso, la variable de estado contendrá "Washington" y la variable City contendrá "Redmond. Microsoft".</span><span class="sxs-lookup"><span data-stu-id="3feaf-199">In the latter case, the state variable will contain "Washington" and the city variable will contain "Redmond.Microsoft".</span></span> <span data-ttu-id="3feaf-200">En este caso, cualquier texto (salvo ‘/’) coincidirá con la variable {ciudad}.</span><span class="sxs-lookup"><span data-stu-id="3feaf-200">In this case any text (except ‘/’) will match the {city} variable.</span></span> <span data-ttu-id="3feaf-201">Si desea que una plantilla no coincida con el texto "extra", coloque la variable en un segmento de plantilla independiente, por ejemplo: "Addresses/{State}/{City}.</span><span class="sxs-lookup"><span data-stu-id="3feaf-201">If you want a template that will not match the "extra" text, place the variable in a separate template segment, for example: "Addresses/{state}/{city}.</span></span>  
  
### <a name="named-wildcard-segments"></a><span data-ttu-id="3feaf-202">Segmentos de carácter comodín con nombre</span><span class="sxs-lookup"><span data-stu-id="3feaf-202">Named Wildcard Segments</span></span>  

 <span data-ttu-id="3feaf-203">Un segmento de carácter comodín con nombre es cualquier segmento de variable de ruta de acceso cuyo nombre de variable comienza con el carácter comodín ' \* '.</span><span class="sxs-lookup"><span data-stu-id="3feaf-203">A named wildcard segment is any path variable segment whose variable name begins with the wildcard character ‘\*’.</span></span> <span data-ttu-id="3feaf-204">La cadena de plantilla siguiente contiene un segmento de carácter comodín con nombre denominado "zapato".</span><span class="sxs-lookup"><span data-stu-id="3feaf-204">The following template string contains a named wildcard segment named "shoe".</span></span>  
  
`"literal/{*shoe}"`  
  
 <span data-ttu-id="3feaf-205">Los segmentos de carácter comodín deben seguir las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3feaf-205">Wildcard segments must follow the following rules:</span></span>  
  
- <span data-ttu-id="3feaf-206">Puede haber a lo sumo un segmento de carácter comodín con nombre para cada cadena de plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-206">There can be at most one named wildcard segment for each template string.</span></span>  
  
- <span data-ttu-id="3feaf-207">Un segmento de carácter comodín con nombre debe aparecer en el segmento situado en el extremo derecho de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3feaf-207">A named wildcard segment must appear at the right-most segment in the path.</span></span>  
  
- <span data-ttu-id="3feaf-208">Un segmento de carácter comodín con nombre no puede coexistir con un segmento de carácter comodín anónimo dentro de la misma cadena de plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-208">A named wildcard segment cannot coexist with an anonymous wildcard segment within the same template string.</span></span>  
  
- <span data-ttu-id="3feaf-209">El nombre de un segmento de carácter comodín con nombre debe ser único.</span><span class="sxs-lookup"><span data-stu-id="3feaf-209">The name of a named wildcard segment must be unique.</span></span>  
  
- <span data-ttu-id="3feaf-210">Los segmentos de carácter comodín con nombre no pueden tener valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3feaf-210">Named wildcard segments cannot have default values.</span></span>  
  
- <span data-ttu-id="3feaf-211">Los segmentos comodín con nombre no pueden terminar con "/".</span><span class="sxs-lookup"><span data-stu-id="3feaf-211">Named wildcard segments cannot end with "/".</span></span>  
  
### <a name="default-variable-values"></a><span data-ttu-id="3feaf-212">Valores de variable predeterminados</span><span class="sxs-lookup"><span data-stu-id="3feaf-212">Default Variable Values</span></span>  

 <span data-ttu-id="3feaf-213">Los valores de variable predeterminados permiten especificar valores predeterminados para las variables de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-213">Default variable values allow you to specify default values for variables within a template.</span></span> <span data-ttu-id="3feaf-214">Las variables predeterminadas se pueden especificar con las llaves que declaran la variable o como una colección pasada al constructor UriTemplate.</span><span class="sxs-lookup"><span data-stu-id="3feaf-214">Default variables can be specified with the curly braces that declare the variable or as a collection passed to the UriTemplate constructor.</span></span> <span data-ttu-id="3feaf-215">La plantilla siguiente muestra dos maneras de especificar <xref:System.UriTemplate> con variables con valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3feaf-215">The following template shows two ways to specify a <xref:System.UriTemplate> with variables with default values.</span></span>  
  
```csharp
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 <span data-ttu-id="3feaf-216">Esta plantilla declara una variable denominada `a` con un valor predeterminado de `1` y una variable denominada `b` con un valor predeterminado de `5`.</span><span class="sxs-lookup"><span data-stu-id="3feaf-216">This template declares a variable named `a` with a default value of `1` and a variable named `b` with a default value of `5`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3feaf-217">Solo las variables de segmento de ruta de acceso pueden tener valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3feaf-217">Only path segment variables are allowed to have default values.</span></span> <span data-ttu-id="3feaf-218">No se permite que tengan valores predeterminados las variables de cadena de consulta, las variables de segmentos compuestos y las variables de carácter comodín con nombre.</span><span class="sxs-lookup"><span data-stu-id="3feaf-218">Query string variables, compound segment variables, and named wildcard variables are not permitted to have default values.</span></span>  
  
 <span data-ttu-id="3feaf-219">En el código siguiente se muestra cómo se administran los valores de variable predeterminados cuando se buscan coincidencias con un URI candidato.</span><span class="sxs-lookup"><span data-stu-id="3feaf-219">The following code shows how default variable values are handled when matching a candidate URI.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");

UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);
Uri candidate = new Uri("http://localhost:8000/OR");

UriTemplateMatch m1 = t.Match(baseAddress, candidate);

Console.WriteLine($"Template: {t}");
Console.WriteLine($"Candidate URI: {candidate}");

// Display contents of BoundVariables
Console.WriteLine("BoundVariables:");
foreach (string key in m1.BoundVariables.AllKeys)
{
    Console.WriteLine($"\t{key}={m1.BoundVariables[key]}");
}
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/
// Candidate URI: http://localhost:8000/OR
// BoundVariables:
//         STATE=OR
//         CITY=Redmond
```  
  
> [!NOTE]
> <span data-ttu-id="3feaf-220">Un URI como no `http://localhost:8000///` coincide con la plantilla indicada en el código anterior, pero un URI como `http://localhost:8000/` sí.</span><span class="sxs-lookup"><span data-stu-id="3feaf-220">A URI such as `http://localhost:8000///` does not match the template listed in the preceding code, however a URI such as `http://localhost:8000/` does.</span></span>  
  
 <span data-ttu-id="3feaf-221">En el código siguiente se muestra cómo se administran los valores de variable predeterminados al crear un URI con una plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-221">The following code shows how default variable values are handled when creating a URI with a template.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
<span data-ttu-id="3feaf-222">Cuando se proporciona a una variable un valor predeterminado de `null`, hay algunas restricciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="3feaf-222">When a variable is given a default value of `null` there are some additional constraints.</span></span> <span data-ttu-id="3feaf-223">Una variable puede tener un valor predeterminado de `null` si la variable se incluye dentro del segmento situado más a la derecha de la cadena de la plantilla o si todos los segmentos a la derecha del segmento tienen valores predeterminados de `null`.</span><span class="sxs-lookup"><span data-stu-id="3feaf-223">A variable can have a default value of `null` if the variable is contained within the right most segment of the template string or if all segments to the right of the segment have default values of `null`.</span></span> <span data-ttu-id="3feaf-224">A continuación se muestran cadenas de plantilla válidas con valores predeterminados de `null`:</span><span class="sxs-lookup"><span data-stu-id="3feaf-224">The following are valid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("shoe/{boat=null}");`

- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");`
  
- `UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");`

 <span data-ttu-id="3feaf-225">Las siguientes son cadenas de plantilla no válidas con valores predeterminados de `null` :</span><span class="sxs-lookup"><span data-stu-id="3feaf-225">The following are invalid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment`
  
- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value`

### <a name="default-values-and-matching"></a><span data-ttu-id="3feaf-226">Valores predeterminados y coincidencias</span><span class="sxs-lookup"><span data-stu-id="3feaf-226">Default Values and Matching</span></span>  

 <span data-ttu-id="3feaf-227">Al comparar un URI candidato con una plantilla que tiene valores predeterminados, si los valores no se especifican en el URI candidato, los valores predeterminados se colocan en la colección <xref:System.UriTemplateMatch.BoundVariables%2A>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-227">When matching a candidate URI with a template that has default values, the default values are placed in the <xref:System.UriTemplateMatch.BoundVariables%2A> collection if values are not specified in the candidate URI.</span></span>  
  
### <a name="template-equivalence"></a><span data-ttu-id="3feaf-228">Equivalencia de plantillas</span><span class="sxs-lookup"><span data-stu-id="3feaf-228">Template Equivalence</span></span>  

 <span data-ttu-id="3feaf-229">Se dice que dos plantillas son *estructuralmente equivalentes* cuando todos los literales de las plantillas coinciden y tienen variables en los mismos segmentos.</span><span class="sxs-lookup"><span data-stu-id="3feaf-229">Two templates are said to be *structurally equivalent* when all of the templates' literals match and they have variables in the same segments.</span></span> <span data-ttu-id="3feaf-230">Por ejemplo, las siguientes plantillas son estructuralmente equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3feaf-230">For example the following templates are structurally equivalent:</span></span>  
  
- <span data-ttu-id="3feaf-231">/a/{Var1}/b b/{Var2}? x = 1&y = 2</span><span class="sxs-lookup"><span data-stu-id="3feaf-231">/a/{var1}/b b/{var2}?x=1&y=2</span></span>  
  
- <span data-ttu-id="3feaf-232">a/{x}/b% 20B/{Var1}? y = 2&x = 1</span><span class="sxs-lookup"><span data-stu-id="3feaf-232">a/{x}/b%20b/{var1}?y=2&x=1</span></span>  
  
- <span data-ttu-id="3feaf-233">a/{y}/B% 20B/{z}/? y = 2&x = 1</span><span class="sxs-lookup"><span data-stu-id="3feaf-233">a/{y}/B%20B/{z}/?y=2&x=1</span></span>  
  
 <span data-ttu-id="3feaf-234">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3feaf-234">A few things to notice:</span></span>  
  
- <span data-ttu-id="3feaf-235">Si una plantilla contiene guiones al principio, solo se pasa por alto el primero.</span><span class="sxs-lookup"><span data-stu-id="3feaf-235">If a template contains leading slashes, only the first one is ignored.</span></span>  
  
- <span data-ttu-id="3feaf-236">Al comparar las cadenas de plantillas para ver la equivalencia estructural, se ignoran las mayúsculas/minúsculas de los nombres de las variables y segmentos de rutas, mientras que sí se tienen en cuenta en las cadenas de consulta.</span><span class="sxs-lookup"><span data-stu-id="3feaf-236">When comparing template strings for structural equivalence, case is ignored for variable names and path segments, query strings are case sensitive.</span></span>  
  
- <span data-ttu-id="3feaf-237">Las cadenas de consulta no están ordenadas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-237">Query strings are unordered.</span></span>  
  
## <a name="uritemplatetable"></a><span data-ttu-id="3feaf-238">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="3feaf-238">UriTemplateTable</span></span>  

 <span data-ttu-id="3feaf-239">La clase <xref:System.UriTemplateTable> representa una tabla asociativa de objetos <xref:System.UriTemplate> enlazada a un objeto elegido por el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="3feaf-239">The <xref:System.UriTemplateTable> class represents an associative table of <xref:System.UriTemplate> objects bound to an object of the developer's choosing.</span></span> <span data-ttu-id="3feaf-240">Un <xref:System.UriTemplateTable> debe contener por lo menos una <xref:System.UriTemplate> antes de llamar a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-240">A <xref:System.UriTemplateTable> must contain at least one <xref:System.UriTemplate> prior to calling <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span> <span data-ttu-id="3feaf-241">El contenido de <xref:System.UriTemplateTable> se puede cambiar hasta que se llame a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-241">The contents of a <xref:System.UriTemplateTable> can be changed until <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="3feaf-242">Se realiza la validación cuando se llama a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-242">Validation is performed when <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="3feaf-243">El tipo de validación realizada depende del valor del parámetro `allowMultiple` para <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-243">The type of validation performed depends upon the value of the `allowMultiple` parameter to <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span>  
  
 <span data-ttu-id="3feaf-244">Cuando se llama <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> y pasa `false`, la <xref:System.UriTemplateTable> comprueba que no hay plantillas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-244">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `false`, the <xref:System.UriTemplateTable> checks to make sure there are no templates in the table.</span></span> <span data-ttu-id="3feaf-245">Si encuentra plantillas estructuralmente equivalentes, produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="3feaf-245">If it finds any structurally equivalent templates, it throws an exception.</span></span> <span data-ttu-id="3feaf-246">Esto se utiliza junto con <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> cuando desee asegurarse de que solo una plantilla coincide con un URI de entrada.</span><span class="sxs-lookup"><span data-stu-id="3feaf-246">This is used in conjunction with <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> when you want to ensure only one template matches an incoming URI.</span></span>  
  
 <span data-ttu-id="3feaf-247">Cuando se llama a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> y se pasa `true`, <xref:System.UriTemplateTable> permite que varias plantillas estructuralmente equivalentes estén contenidas dentro de <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-247">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `true`, <xref:System.UriTemplateTable> allows multiple, structurally-equivalent templates to be contained within a <xref:System.UriTemplateTable>.</span></span>  
  
 <span data-ttu-id="3feaf-248">Si un conjunto de objetos <xref:System.UriTemplate> agregados a <xref:System.UriTemplateTable> contienen cadenas de consulta, no deben ser ambiguas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-248">If a set of <xref:System.UriTemplate> objects added to a <xref:System.UriTemplateTable> contain query strings they must not be ambiguous.</span></span> <span data-ttu-id="3feaf-249">Se permiten cadenas de consulta idénticas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-249">Identical query strings are allowed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3feaf-250">Mientras <xref:System.UriTemplateTable> permite direcciones base que utilizan esquemas que no sean HTTP, se omiten el esquema y el número de puerto al comparar los URI candidatos con las plantillas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-250">While the <xref:System.UriTemplateTable> allows base addresses that use schemes other than HTTP, the scheme and port number are ignored when matching candidate URIs to templates.</span></span>  
  
### <a name="query-string-ambiguity"></a><span data-ttu-id="3feaf-251">Ambigüedad de cadenas de consulta</span><span class="sxs-lookup"><span data-stu-id="3feaf-251">Query String Ambiguity</span></span>  

 <span data-ttu-id="3feaf-252">Las plantillas que comparten una ruta de acceso equivalente contienen cadenas de consulta ambiguas si hay un URI que coincida con más de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="3feaf-252">Templates that share an equivalent path contain ambiguous query strings if there is a URI that matches more than one template.</span></span>  
  
 <span data-ttu-id="3feaf-253">Los siguientes conjuntos de cadenas de consulta no son ambiguos entre ellos:</span><span class="sxs-lookup"><span data-stu-id="3feaf-253">The following sets of query strings are unambiguous within themselves:</span></span>  
  
- <span data-ttu-id="3feaf-254">?x=1</span><span class="sxs-lookup"><span data-stu-id="3feaf-254">?x=1</span></span>  
  
- <span data-ttu-id="3feaf-255">?x=2</span><span class="sxs-lookup"><span data-stu-id="3feaf-255">?x=2</span></span>  
  
- <span data-ttu-id="3feaf-256">?x=3</span><span class="sxs-lookup"><span data-stu-id="3feaf-256">?x=3</span></span>  
  
- <span data-ttu-id="3feaf-257">? x = 1&y = {var}</span><span class="sxs-lookup"><span data-stu-id="3feaf-257">?x=1&y={var}</span></span>  
  
- <span data-ttu-id="3feaf-258">? x = 2&z = {var}</span><span class="sxs-lookup"><span data-stu-id="3feaf-258">?x=2&z={var}</span></span>  
  
- <span data-ttu-id="3feaf-259">?x=3</span><span class="sxs-lookup"><span data-stu-id="3feaf-259">?x=3</span></span>  
  
- <span data-ttu-id="3feaf-260">?x=1</span><span class="sxs-lookup"><span data-stu-id="3feaf-260">?x=1</span></span>  
  
- <span data-ttu-id="3feaf-261">?</span><span class="sxs-lookup"><span data-stu-id="3feaf-261">?</span></span>  
  
- <span data-ttu-id="3feaf-262">?</span><span class="sxs-lookup"><span data-stu-id="3feaf-262">?</span></span> <span data-ttu-id="3feaf-263">x={var}</span><span class="sxs-lookup"><span data-stu-id="3feaf-263">x={var}</span></span>  
  
- <span data-ttu-id="3feaf-264">?</span><span class="sxs-lookup"><span data-stu-id="3feaf-264">?</span></span>  
  
- <span data-ttu-id="3feaf-265">? m = Get&c = RSS</span><span class="sxs-lookup"><span data-stu-id="3feaf-265">?m=get&c=rss</span></span>  
  
- <span data-ttu-id="3feaf-266">? m = Put&c = RSS</span><span class="sxs-lookup"><span data-stu-id="3feaf-266">?m=put&c=rss</span></span>  
  
- <span data-ttu-id="3feaf-267">? m = Get&c = Atom</span><span class="sxs-lookup"><span data-stu-id="3feaf-267">?m=get&c=atom</span></span>  
  
- <span data-ttu-id="3feaf-268">? m = Put&c = Atom</span><span class="sxs-lookup"><span data-stu-id="3feaf-268">?m=put&c=atom</span></span>  
  
 <span data-ttu-id="3feaf-269">Los siguientes conjuntos de plantillas de cadenas de consulta no son ambiguas entre ellas:</span><span class="sxs-lookup"><span data-stu-id="3feaf-269">The following sets of query string templates are ambiguous within themselves:</span></span>  
  
- <span data-ttu-id="3feaf-270">?x=1</span><span class="sxs-lookup"><span data-stu-id="3feaf-270">?x=1</span></span>  
  
- <span data-ttu-id="3feaf-271">?x={var}</span><span class="sxs-lookup"><span data-stu-id="3feaf-271">?x={var}</span></span>  
  
 <span data-ttu-id="3feaf-272">"x=1": coincide con ambas plantillas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-272">"x=1" - Matches both templates.</span></span>  
  
- <span data-ttu-id="3feaf-273">?x=1</span><span class="sxs-lookup"><span data-stu-id="3feaf-273">?x=1</span></span>  
  
- <span data-ttu-id="3feaf-274">?y=2</span><span class="sxs-lookup"><span data-stu-id="3feaf-274">?y=2</span></span>  
  
 <span data-ttu-id="3feaf-275">"x = 1&y = 2" coincide con ambas plantillas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-275">"x=1&y=2" matches both templates.</span></span> <span data-ttu-id="3feaf-276">Esto se debe a que una cadena de consulta puede contener más variables de cadenas de consulta que la plantilla con la que coincide.</span><span class="sxs-lookup"><span data-stu-id="3feaf-276">This is because a query string may contain more query string variables then the template it matches.</span></span>  
  
- <span data-ttu-id="3feaf-277">?x=1</span><span class="sxs-lookup"><span data-stu-id="3feaf-277">?x=1</span></span>  
  
- <span data-ttu-id="3feaf-278">? x = 1&y = {var}</span><span class="sxs-lookup"><span data-stu-id="3feaf-278">?x=1&y={var}</span></span>  
  
 <span data-ttu-id="3feaf-279">"x = 1&y = 3" coincide con ambas plantillas.</span><span class="sxs-lookup"><span data-stu-id="3feaf-279">"x=1&y=3" matches both templates.</span></span>  
  
- <span data-ttu-id="3feaf-280">? x = 3&y = 4</span><span class="sxs-lookup"><span data-stu-id="3feaf-280">?x=3&y=4</span></span>  
  
- <span data-ttu-id="3feaf-281">? x = 3&z = 5</span><span class="sxs-lookup"><span data-stu-id="3feaf-281">?x=3&z=5</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3feaf-282">Se considera que los caracteres á y Á son diferentes cuando aparecen como parte de una ruta URI o literal de segmento de ruta <xref:System.UriTemplate> (pero los caracteres a y A se considera que son iguales).</span><span class="sxs-lookup"><span data-stu-id="3feaf-282">The characters á and Á are considered to be different characters when they appear as part of a URI path or <xref:System.UriTemplate> path segment literal (but the characters a and A are considered to be the same).</span></span> <span data-ttu-id="3feaf-283">Se considera que los caracteres á y Á son caracteres diferentes cuando aparecen como parte de una <xref:System.UriTemplate> {variableName} o una cadena de consulta (y también se considera que a y A son los mismos caracteres).</span><span class="sxs-lookup"><span data-stu-id="3feaf-283">The characters á and Á are considered to be the same characters when they appear as part of a <xref:System.UriTemplate> {variableName} or a query string (and a and A are also considered to be the same characters).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3feaf-284">Vea también</span><span class="sxs-lookup"><span data-stu-id="3feaf-284">See also</span></span>

- [<span data-ttu-id="3feaf-285">Información general del modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="3feaf-285">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
- [<span data-ttu-id="3feaf-286">Modelo de objetos de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="3feaf-286">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
- [<span data-ttu-id="3feaf-287">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="3feaf-287">UriTemplate</span></span>](../samples/uritemplate-sample.md)
- [<span data-ttu-id="3feaf-288">Tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="3feaf-288">UriTemplate Table</span></span>](../samples/uritemplate-table-sample.md)
- [<span data-ttu-id="3feaf-289">Distribuidor de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="3feaf-289">UriTemplate Table Dispatcher</span></span>](../samples/uritemplate-table-dispatcher-sample.md)
