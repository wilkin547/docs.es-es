---
title: "UriTemplate y UriTemplateTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# UriTemplate y UriTemplateTable
Los desarrolladores web necesitan poder describir la forma y el diseño de los URI a los que sus servicios responden.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] agregó dos nuevas clases para proporcionar a los desarrolladores el control sobre sus URI.<xref:System.UriTemplate> y <xref:System.UriTemplateTable> forman la base del motor de distribución basado en URI en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Estas clases también se pueden utilizar por sí mismas, permitiendo a los desarrolladores aprovecharse de las plantillas y el mecanismo de asignación de URI sin implementar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Plantillas  
 Una plantilla es una manera de describir un conjunto de URI relativos.El conjunto de plantillas URI de la tabla siguiente muestra cómo se podría definir un sistema que recupera varios tipos de información meteorológica.  
  
|Datos|Plantilla|  
|-----------|---------------|  
|Previsión nacional|tiempo\/nacional|  
|Previsión estatal|tiempo\/{estado}|  
|Previsión de la ciudad|tiempo\/{estado}\/{ciudad}|  
|Previsión de Actividad|tiempo\/{estado}\/{ciudad}\/{actividad}|  
  
 Esta tabla describe un conjunto de URI estructuralmente similares.Cada entrada es una plantilla URI.Los segmentos entre llaves describen las variables.Los segmentos que no están entre llaves describen cadenas literales.Las clases de plantillas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permiten a un desarrollador tomar un URI de entrada, como, por ejemplo, "\/tiempo\/wa\/seattle\/ciclismo" e igualarlo a una plantilla que lo describe, "\/tiempo\/{estado}\/{ciudad}\/{actividad}."  
  
## UriTemplate  
 <xref:System.UriTemplate> es una clase que encapsula una plantilla URI.El constructor toma un parámetro de cadena que define la plantilla.Esta cadena contiene la plantilla en el formato descrito en la sección siguiente.La clase <xref:System.UriTemplate> proporciona métodos que le permiten igualar un URI de entrada a una plantilla, generar un URI a partir de una plantilla, recuperar una colección de nombres de variables usadas en la plantilla, determinar si dos plantillas son equivalentes, y devolver la cadena de la plantilla.  
  
 <xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> toma una dirección base y un candidato a identificador URI e intenta asociar el URI a la plantilla.Si la coincidencia se realiza correctamente, se devuelve una instancia <xref:System.UriTemplateMatch>.El objeto <xref:System.UriTemplateMatch> contiene una dirección URI base, el URI candidato, una colección de nombres\/valores de los parámetros de consulta, una matriz de segmentos de ruta de acceso relativa, una colección de nombres\/valores de variables comparadas, la instancia de <xref:System.UriTemplate> utilizada para la comparación, una cadena que contiene cualquier parte no coincidente del URI candidato \(se usa cuando la plantilla tiene un carácter comodín\) y un objeto que está asociado a la plantilla.  
  
> [!NOTE]
>  La clase <xref:System.UriTemplate> omite el esquema y número de puerto al comparar un URI candidato con una plantilla.  
  
 Hay dos métodos que le permiten generar un URI a partir de una plantilla: <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> y [BindByPosition\(Uri, String\<xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.<xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> toma una dirección base y una colección de nombre y valor de parámetros.Estos parámetros se sustituyen por variables cuando se enlaza la plantilla.[BindByPosition\(Uri, String\<xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> toma los pares de nombre\/valor y los sustituye de izquierda a derecha.  
  
 <xref:System.UriTemplate.ToString> devuelve la cadena de la plantilla.  
  
 La propiedad <xref:System.UriTemplate.PathSegmentVariableNames%2A> contiene una colección de los nombres de las variables usadas dentro de segmentos de ruta de acceso en la cadena de la plantilla.  
  
 <xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> toma <xref:System.UriTemplate> como parámetro y devuelve un valor booleano que especifica si las dos plantillas son equivalentes.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] la sección Equivalencia de plantillas más adelante en este tema.  
  
 <xref:System.UriTemplate> está diseñado para funcionar con cualquier esquema de URI que cumpla la gramática de URI de HTTP.A continuación se ofrecen ejemplos de esquemas de URI compatibles.  
  
-   http:\/\/  
  
-   https:\/\/  
  
-   net.tcp:\/\/  
  
-   net.pipe:\/\/  
  
-   sb:\/\/  
  
 Esquemas como file:\/\/ y urn:\/\/ no cumplen la gramática de URI de HTTP y producen resultados imprevisibles cuando se usan con plantillas URI.  
  
### Sintaxis de cadenas de plantillas  
 Una plantilla tiene tres partes: una ruta de acceso, una consulta opcional y un fragmento opcional.Para obtener un ejemplo, vea la plantilla siguiente:  
  
```  
"/weather/{state}/{city}?forecast={length)#frag1  
```  
  
 La ruta de acceso consiste de "\/tiempo\/{estado}\/{ciudad}", la consulta consiste de"? previsión\={longitud} y el fragmento consiste de "\#frag1."  
  
 Las barras diagonales iniciales y finales son opcionales en la expresión de la ruta de acceso.Se pueden omitir completamente las expresiones de consulta y fragmento.Una ruta de acceso está compuesta de una serie de segmentos delimitados por '\/', cada segmento puede tener un valor literal, un nombre de variable \(se escribe entre {llaves}\) o un carácter comodín \(escrito como '\*'\).En la plantilla anterior el segmento “\\tiempo\\” es un valor literal mientras que “{estado}” y “{ciudad}” son las variables.Las variables toman su nombre a partir del contenido de sus llaves y se pueden reemplazar después con un valor concreto para crear un *URI cerrado*.El carácter comodín es opcional, pero solo puede aparecer al final del URI, donde coincide lógicamente con “el resto de la ruta de acceso”.  
  
 La expresión de consulta, si está presente, especifica una serie de pares nombre\-valor no ordenados delimitados por '&'.Los elementos de la expresión de consulta pueden ser pares literales \(x\=2\) o un par de variables \(x \= {var}\).Solo el lado derecho de la consulta puede tener una expresión variable.\({someName} \= {someValue} no está permitido.No se permiten los valores no emparejados \(? x\).No hay ninguna diferencia entre una expresión de consulta vacía y una expresión de consulta compuesta de un único '?'. \(ambos significan “cualquier consulta”\).  
  
 La expresión de fragmento puede estar compuesta de un valor literal; no se permiten variables.  
  
 Todos los nombres de variables de la plantilla dentro de una cadena de la plantilla deben ser únicos.Los nombres de variables de la plantilla no distinguen entre mayúsculas y minúsculas.  
  
 Ejemplos de cadenas de plantillas válidas:  
  
-   ""  
  
-   "\/zapato"  
  
-   "\/zapato\/\*"  
  
-   "{zapato}\/barco"  
  
-   “{zapato}\/{barco}\/cama\/{edredón}”  
  
-   “zapato\/{barco}”  
  
-   “zapato\/{barco}\/\*”  
  
-   “zapato\/barco?x\=2”  
  
-   “zapato\/{barco}?x\={cama}”  
  
-   "zapato\/{barco}?x\={cama}&y\=banda"  
  
-   “?x\={zapato}”  
  
-   "zapato?x\=3&y\={var}  
  
 Ejemplos de cadenas de plantillas no válidas:  
  
-   “{zapato}\/{ZAPATO}\/x\=2”: nombres de variables duplicados.  
  
-   “{zapato}\/barco\/?cama\={zapato}”: nombres de variables duplicados.  
  
-   “?x\=2&x\=3”: los pares nombre\-valor de una cadena de consulta deben ser únicos, aunque sean literales.  
  
-   “? x\=2&”: la cadena de consulta tiene un formato incorrecto.  
  
-   "?2&x\={zapato}": la cadena de consulta debe estar formada por pares nombre\-valor.  
  
-   “?y\=2&&X\=3”: la cadena de consulta debe estar formada por pares nombre\-valor, y los nombres no pueden comenzar por "&".  
  
### Segmentos de ruta de acceso compuestos  
 Los segmentos de ruta de acceso compuestos permiten que un solo segmento de ruta de acceso de URI contenga varias variables y variables combinadas con literales.A continuación, se ofrecen ejemplos de segmentos de ruta de acceso compuestos válidos.  
  
-   \/nombreDeArchivo.{ext}\/  
  
-   \/{nombreDeArchivo}.jpg\/  
  
-   \/{nombreDeArchivo}.{ext}\/  
  
-   \/{a}.{b}algúnLiteral{c}\({d}\)\/  
  
 A continuación, se ofrecen ejemplos de segmentos de ruta de acceso no válidos.  
  
-   \/{}: a las variables se les debe asignar un nombre.  
  
-   \/{zapato}{barco}: las variables deben estar separadas por un literal.  
  
### Segmentos de ruta de acceso coincidentes y compuestos  
 Los segmentos de ruta de acceso permiten definir un UriTemplate que tenga varias variables en un solo segmento de ruta de acceso.Por ejemplo, en la siguiente cadena de plantilla: “Direcciones\/{estado}.{ciudad}” se definen dos variables \(estado y ciudad\) en el mismo segmento.Esta plantilla coincidiría con una URL como “http:\/\/example.com\/Washington.Redmond” pero también lo haría con una URL como “http:\/\/example.com\/Washington.Redmond.Microsoft”.En el último caso, la variable de estado contendrá “Washington” y la de ciudad, “Redmond.Microsoft”.En este caso, cualquier texto \(salvo ‘\/’\) coincidirá con la variable {ciudad}.Si desea una plantilla que no coincida con el texto “extra”, coloque la variable en un segmento de plantilla independiente, por ejemplo: “Direcciones\/{estado}\/{ciudad}.  
  
### Segmentos de carácter comodín con nombre  
 Un segmento de carácter comodín con nombre es cualquier segmento de variable de ruta de acceso cuyo nombre de variable comience por el carácter comodín "\*".La cadena de plantilla siguiente contiene un segmento de carácter comodín con nombre denominado "zapato".  
  
```  
"literal/{*shoe}"  
```  
  
 Los segmentos de carácter comodín deben seguir las reglas siguientes:  
  
-   Puede haber a lo sumo un segmento de carácter comodín con nombre para cada cadena de plantilla.  
  
-   Un segmento de carácter comodín con nombre debe aparecer en el segmento situado en el extremo derecho de la ruta de acceso.  
  
-   Un segmento de carácter comodín con nombre no puede coexistir con un segmento de carácter comodín anónimo dentro de la misma cadena de plantilla.  
  
-   El nombre de un segmento de carácter comodín con nombre debe ser único.  
  
-   Los segmentos de carácter comodín con nombre no pueden tener valores predeterminados.  
  
-   Los segmentos de carácter comodín con nombre no pueden finalizar con "\/".  
  
### Valores de variable predeterminados  
 Los valores de variable predeterminados permiten especificar valores predeterminados para las variables de una plantilla.Las variables predeterminadas se pueden especificar con las llaves que declaran la variable o como una colección pasada al constructor UriTemplate.La plantilla siguiente muestra dos maneras de especificar <xref:System.UriTemplate> con variables con valores predeterminados.  
  
```  
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 Esta plantilla declara una variable denominada `a` con un valor predeterminado de `1` y una variable denominada `b` con un valor predeterminado de `5`.  
  
> [!NOTE]
>  Solo las variables de segmento de ruta de acceso pueden tener valores predeterminados.No se permite que tengan valores predeterminados las variables de cadena de consulta, las variables de segmentos compuestos y las variables de carácter comodín con nombre.  
  
 En el código siguiente se muestra cómo se administran los valores de variable predeterminados cuando se buscan coincidencias con un URI candidato.  
  
```  
Uri baseAddress = new Uri("http://localhost:800   
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);0");  
UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);  
Uri candidate = new Uri("http://localhost:8000/OR");  
  
UriTemplateMatch m1 = t.Match(baseAddress, candidate);  
  
// Display contents of BoundVariables  
foreach (string key in m1.BoundVariables.AllKeys)  
{  
    Console.WriteLine("\t\t{0}={1}", key, m1.BoundVariables[key]);  
}  
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/  
// Candidate URI: http://localhost:8000/OR  
// BoundVariables:  
//      STATE=OR  
//       CITY=Redmond  
  
```  
  
> [!NOTE]
>  Un URI como http:\/\/localhost:8000\/\/\/ no coincide con la plantilla que aparece en el código anterior, pero sí lo hará un URI como http:\/\/localhost:8000\/.  
  
 En el código siguiente se muestra cómo se administran los valores de variable predeterminados al crear un URI con una plantilla.  
  
```  
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
  
 Cuando se proporciona a una variable un valor predeterminado de `null`, hay algunas restricciones adicionales.Una variable puede tener un valor predeterminado de `null` si la variable se incluye dentro del segmento situado más a la derecha de la cadena de la plantilla o si todos los segmentos a la derecha del segmento tienen valores predeterminados de `null`.A continuación se muestran cadenas de plantilla válidas con valores predeterminados de `null`:  
  
-   ```  
    UriTemplate t = new UriTemplate("shoe/{boat=null}");  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");  
    ```  
  
 A continuación se muestran cadenas de plantilla no válidas con valores predeterminados de `null`:  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value  
    ```  
  
### Valores predeterminados y coincidencias  
 Al comparar un URI candidato con una plantilla que tiene valores predeterminados, si los valores no se especifican en el URI candidato, los valores predeterminados se colocan en la colección <xref:System.UriTemplateMatch.BoundVariables%2A>.  
  
### Equivalencia de plantillas  
 Se dice que dos plantillas son *estructuralmente equivalentes* cuando todos los literales de las plantillas coinciden y tienen variables en los mismos segmentos.Por ejemplo, las siguientes plantillas son estructuralmente equivalentes:  
  
-   \/a\/{var1}\/b b\/{var2}?x\=1&y\=2  
  
-   a\/{x}\/b%20b\/{var1}?y\=2&x\=1  
  
-   a\/{y}\/B%20B\/{z}\/?y\=2&x\=1  
  
 Tenga en cuenta lo siguiente:  
  
-   Si una plantilla contiene guiones al principio, solo se pasa por alto el primero.  
  
-   Al comparar las cadenas de plantillas para ver la equivalencia estructural, se ignoran las mayúsculas\/minúsculas de los nombres de las variables y segmentos de rutas, mientras que sí se tienen en cuenta en las cadenas de consulta.  
  
-   Las cadenas de consulta no están ordenadas.  
  
## UriTemplateTable  
 La clase <xref:System.UriTemplateTable> representa una tabla asociativa de objetos <xref:System.UriTemplate> enlazada a un objeto elegido por el desarrollador.Un <xref:System.UriTemplateTable> debe contener por lo menos una <xref:System.UriTemplate> antes de llamar a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.El contenido de <xref:System.UriTemplateTable> se puede cambiar hasta que se llame a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.Se realiza la validación cuando se llama a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.El tipo de validación realizada depende del valor del parámetro `allowMultiple` para <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.  
  
 Cuando se llama <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> y pasa `false`, la <xref:System.UriTemplateTable> comprueba que no hay plantillas en la tabla.Si encuentra plantillas estructuralmente equivalentes, produce una excepción.Esto se utiliza junto con <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> cuando desee asegurarse de que solo una plantilla coincide con un URI de entrada.  
  
 Cuando se llama a <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> y se pasa `true`, <xref:System.UriTemplateTable> permite que varias plantillas estructuralmente equivalentes estén contenidas dentro de <xref:System.UriTemplateTable>.  
  
 Si un conjunto de objetos <xref:System.UriTemplate> agregados a <xref:System.UriTemplateTable> contienen cadenas de consulta, no deben ser ambiguas.Se permiten cadenas de consulta idénticas.  
  
> [!NOTE]
>  Mientras <xref:System.UriTemplateTable> permite direcciones base que utilizan esquemas que no sean HTTP, se omiten el esquema y el número de puerto al comparar los URI candidatos con las plantillas.  
  
### Ambigüedad de cadenas de consulta  
 Las plantillas que comparten una ruta de acceso equivalente contienen cadenas de consulta ambiguas si hay un URI que coincida con más de una plantilla.  
  
 Los siguientes conjuntos de cadenas de consulta no son ambiguos entre ellos:  
  
-   ?x\=1  
  
-   ?x\=2  
  
-   ?x\=3  
  
-   ?x\=1&y\={var}  
  
-   ?x\=2&z\={var}  
  
-   ?x\=3  
  
-   ?x\=1  
  
-   ?  
  
-   ?x\={var}  
  
-   ?  
  
-   ?m\=get&c\=rss  
  
-   ?m\=put&c\=rss  
  
-   ?m\=get&c\=atom  
  
-   ?m\=put&c\=atom  
  
 Los siguientes conjuntos de plantillas de cadenas de consulta no son ambiguas entre ellas:  
  
-   ?x\=1  
  
-   ?x\={var}  
  
 "x\=1": coincide con ambas plantillas.  
  
-   ?x\=1  
  
-   ?y\=2  
  
 "x\=1&y\=2" coincide con ambas plantillas.Esto se debe a que una cadena de consulta puede contener más variables de cadenas de consulta que la plantilla con la que coincide.  
  
-   ?x\=1  
  
-   ?x\=1&y\={var}  
  
 "x\=1&y\=3" coincide con ambas plantillas.  
  
-   ?x\=3&y\=4  
  
-   ?x\=3&z\=5  
  
> [!NOTE]
>  Se considera que los caracteres á y Á son diferentes cuando aparecen como parte de una ruta URI o literal de segmento de ruta <xref:System.UriTemplate> \(pero los caracteres a y A se considera que son iguales\).Se considera que los caracteres á y Á son caracteres diferentes cuando aparecen como parte de una <xref:System.UriTemplate> {variableName} o una cadena de consulta \(y también se considera que a y A son los mismos caracteres\).  
  
## Vea también  
 [Información general del modelo de programación web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)   
 [Modelo de objetos de programación web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)   
 [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)   
 [Tabla UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)   
 [Distribuidor de tabla de UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)