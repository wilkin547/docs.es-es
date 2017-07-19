---
title: "Specifying Fully Qualified Type Names | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "names [.NET Framework], fully qualified type names"
  - "reflection, fully qualified type names"
  - "names [.NET Framework], assemblies"
  - "tokens"
  - "BNF"
  - "assemblies [.NET Framework], names"
  - "Backus-Naur form"
  - "languages, BNF grammar"
  - "fully qualified type names"
  - "type names"
  - "special characters"
  - "IDENTIFIER"
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Specifying Fully Qualified Type Names
Es preciso especificar los nombres de tipo para tener entradas válidas en varias operaciones de reflexión.  Un nombre de tipo completo se compone de una especificación de nombre de ensamblado, una especificación de espacio de nombres y un nombre de tipo.  Los métodos como <xref:System.Type.GetType%2A?displayProperty=fullName>, <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName> y <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> utilizan especificaciones de nombres de tipos.  
  
## Gramática del formulario Backus\-Naur para nombres de tipo  
 El formulario Backus\-Naur \(BNF\) define la sintaxis de los lenguajes formales.  La tabla que se muestra a continuación enumera las reglas léxicas BNF que describen cómo reconocer una entrada válida.  Los elementos terminales, que son aquellos elementos que ya no se pueden reducir, aparecen en mayúsculas.  Los elementos no terminales, que son aquellos elementos que aún se pueden reducir, aparecen en mayúsculas y minúsculas o como cadenas con comillas simples \('\), pero éstas no forman parte de la sintaxis.  La barra vertical \(&#124;\) indica reglas que tienen subreglas.  
  
|Gramática de BNF de nombres de tipo completos|  
|---------------------------------------------------|  
|TypeSpec                          :\=   ReferenceTypeSpec<br /><br /> &#124;     SimpleTypeSpec|  
|ReferenceTypeSpec: \= SimpleTypeSpec '&'|  
|SimpleTypeSpec                :\=   PointerTypeSpec<br /><br /> &#124;     ArrayTypeSpec<br /><br /> &#124;     TypeName|  
|ReferenceTypeSpec            :\=   SimpleTypeSpec '&'|  
|ArrayTypeSpec                  :\=   SimpleTypeSpec '\[ReflectionDimension\]'<br /><br /> &#124;     SimpleTypeSpec '\[ReflectionEmitDimension\]'|  
|ReflectionDimension           :\=   '\*'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|ReflectionEmitDimension    :\=   '\*'<br /><br /> &#124;     Number '..' Número<br /><br /> &#124;     Number '…'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|Number                            :\=   \[0\-9\]\+|  
|TypeName                         :\=   NamespaceTypeName<br /><br /> &#124;     NamespaceTypeName ',' AssemblyNameSpec|  
|NamespaceTypeName        :\=   NestedTypeName<br /><br /> &#124;     NamespaceSpec '.' NestedTypeName|  
|NestedTypeName               :\=   IDENTIFIER<br /><br /> &#124;     NestedTypeName '\+' IDENTIFIER|  
|NestedTypeName               :\=   IDENTIFIER<br /><br /> &#124;     NamespaceSpec '.' IDENTIFIER|  
|NestedTypeName               :\=   IDENTIFIER<br /><br /> &#124;     IDENTIFIER ',' AssemblyProperties|  
|AssemblyProperties            :\=   AssemblyProperty<br /><br /> &#124;     AssemblyProperties ',' AssemblyProperty|  
|AssemblyProperty              :\=   AssemblyPropertyName '\=' AssemblyPropertyValue|  
  
## Especificar caracteres especiales  
 En un nombre de tipo, IDENTIFIER es cualquier nombre válido determinado por las reglas de un lenguaje.  
  
 Se utiliza la barra diagonal inversa \(\\\) como carácter de escape para separar los siguientes símbolos \(token\) cuando se utilizan como parte de IDENTIFIER.  
  
|Símbolo \(Token\)|Significado|  
|-----------------------|-----------------|  
|\\,|Separador de ensamblados.|  
|\\\+|Separador anidado de tipos.|  
|\\&|Tipo de referencia.|  
|\\\*|Tipo de puntero.|  
|\\\[|Delimitador de las dimensiones de matriz.|  
|\\\]|Delimitador de las dimensiones de matriz.|  
|\\.|Se utiliza la barra diagonal inversa delante de un punto sólo si éste se utiliza en una especificación de matriz.  Los puntos en NamespaceSpec no van acompañados de barra diagonal inversa.|  
|\\\\|Barra diagonal inversa cuando se precisa como literal de cadena.|  
  
 Hay que observar que los espacios son relevantes en todos los componentes de TypeSpec, salvo en AssemblyNameSpec.  En AssemblyNameSpec, los espacios delante del separador ',' son relevantes, pero los espacios detrás del separador ',' no se tienen en cuenta.  
  
 Las clases de reflexión, como <xref:System.Type.FullName%2A?displayProperty=fullName>, devuelven el nombre trastocado de modo que el nombre devuelto puede usarse en una llamada a <xref:System.Type.GetType%2A>, como en `MyType.GetType(myType.FullName)`.  
  
 Por ejemplo, el nombre completo de un tipo puede ser `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.  
  
 Si el espacio de nombres es `Ozzy.Out+Back`, el signo más debe ir precedido de una barra diagonal inversa.  En caso contrario, el analizador lo interpretará como un separador de anidamiento.  La reflexión emitirá esta cadena como `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.  
  
## Especificar nombres de ensamblado  
 La información mínima requerida en una especificación de nombre de ensamblado es el nombre textual \(IDENTIFIER\) del ensamblado.  A continuación de IDENTIFIER puede aparecer una lista de pares de propiedad\/valor separados por comas, tal como se describe en la siguiente tabla.  La nomenclatura de IDENTIFIER debe observar las reglas vigentes para la nomenclatura de archivos.  Para IDENTIFIER, no se distingue entre mayúsculas y minúsculas.  
  
|Nombre de la propiedad|Descripción|Valores permitidos|  
|----------------------------|-----------------|------------------------|  
|**Versión**|Número de versión del ensamblado|*Major.Minor.Build.Revision*, donde *Major*, *Minor*, *Build* y *Revision* son enteros comprendidos entre 0 y 65535, ambos inclusive.|  
|**PublicKey**|Clave pública completa|Valor de cadena de la clave pública completa en formato hexadecimal.  Se especifica una referencia nula \(**Nothing** en Visual Basic\) para indicar explícitamente un ensamblado privado.|  
|**PublicKeyToken**|Símbolo \(token\) de clave pública \(hash de 8 bytes de la clave pública completa\)|Valor de cadena del token de clave pública en formato hexadecimal.  Se especifica una referencia nula \(**Nothing** en Visual Basic\) para indicar explícitamente un ensamblado privado.|  
|**Referencia cultural**|Referencia cultural del ensamblado|Referencia cultural del ensamblado en formato RFC\-1766, o "neutral" para los ensamblados que no dependan del lenguaje \(ensamblados que no sean ensamblados satélite\).|  
|**Personalizar**|Objeto binario grande personalizado \(BLOB\).  Actualmente, sólo se utiliza en ensamblados generados por el [Generador de imágenes nativas \(Ngen\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).|Cadena personalizada que utiliza la herramienta Generador de imágenes nativas para notificar a la caché de ensamblados que el ensamblado que se está instalando es una imagen nativa y, por lo tanto, debe instalarse en la caché de imágenes nativas.  Se denomina asimismo una cadena Zap.|  
  
 En el ejemplo siguiente se muestra un **AssemblyName** de un ensamblado de nombre simple con una referencia cultural predeterminada.  
  
```csharp  
com.microsoft.crypto, Culture=""   
```  
  
 En el ejemplo siguiente se muestra una referencia completamente especificada de un ensamblado de nombre seguro con la referencia cultural "en".  
  
```csharp  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0   
```  
  
 Los ejemplos siguientes muestran un **AssemblyName** parcialmente especificado, que se puede satisfacer mediante un ensamblado de nombre seguro o simple.  
  
```csharp  
com.microsoft.crypto  
com.microsoft.crypto, Culture=""  
com.microsoft.crypto, Culture=en   
```  
  
 Los ejemplos siguientes muestran un **AssemblyName** parcialmente especificado, que se debe satisfacer mediante un ensamblado de nombre simple.  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=null   
com.microsoft.crypto, Culture=en, PublicKeyToken=null  
```  
  
 Los ejemplos siguientes muestran un **AssemblyName** parcialmente especificado, que se debe satisfacer mediante un ensamblado de nombre seguro.  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0  
```  
  
## Especificar punteros  
 SimpleTypeSpec\* representa un puntero no administrado.  Por ejemplo, para obtener un puntero al tipo MyType, hay que usar `Type.GetType("MyType*")`.  Por ejemplo, para obtener un puntero a un puntero al tipo MyType, hay que usar `Type.GetType("MyType**")`.  
  
## Especificar referencias  
 SimpleTypeSpec & representa un puntero o una referencia administrado.  Por ejemplo, para obtener una referencia al tipo MyType, hay que usar `Type.GetType("MyType &")`.  Hay que tener en cuenta que, a diferencia de los punteros, las referencias se limitan a un nivel.  
  
## Especificar matrices  
 En la gramática de BNF, ReflectionEmitDimension se aplica sólo a las definiciones de tipo incompletas recuperadas mediante <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName>.  Las definiciones de tipos incompletas son objetos <xref:System.Reflection.Emit.TypeBuilder> construidos mediante [Reflection.Emit](frlrfSystemReflectionEmit) en los que no se ha llamado a <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=fullName>.  Se puede usar ReflectionDimension para recuperar cualquier definición de tipo que se haya completado; es decir, un tipo que está cargado.  
  
 Se obtiene acceso a las matrices en la reflexión especificando el rango de la matriz:  
  
-   `Type.GetType("MyArray[]")` obtiene una matriz unidimensional con límite inferior 0.  
  
-   `Type.GetType("MyArray[*]")` obtiene una matriz unidimensional con límite inferior desconocido.  
  
-   `Type.GetType("MyArray[][]")` obtiene la matriz de una matriz bidimensional.  
  
-   `Type.GetType("MyArray[*,*]")` y `Type.GetType("MyArray[,]")` obtienen una matriz bidimensional rectangular con límites inferiores desconocidos.  
  
 Hay que tener en cuenta que desde el punto de vista del motor de tiempo de ejecución, `MyArray[] != MyArray[*]`, a excepción de las matrices multidimensionales, las dos notaciones son equivalentes.  Es decir, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` se evalúa como **true**.  
  
 Para **ModuleBuilder.GetType**, `MyArray[0..5]` indica una matriz unidimensional con tamaño 6 y límite inferior 0.  `MyArray[4…]` indica una matriz unidimensional de tamaño desconocido y límite inferior 4.  
  
## Vea también  
 <xref:System.Reflection.AssemblyName>   
 <xref:System.Reflection.Emit.ModuleBuilder>   
 <xref:System.Reflection.Emit.TypeBuilder>   
 <xref:System.Type.FullName%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>   
 [Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)