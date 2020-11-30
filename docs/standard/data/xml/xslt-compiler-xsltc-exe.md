---
title: Compilador XSLT (xsltc.exe)
ms.date: 03/30/2017
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
ms.openlocfilehash: 89e2291cb4eafe9ca9e5001061b960f348fe4719
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720833"
---
# <a name="xslt-compiler-xsltcexe"></a>Compilador XSLT (xsltc.exe)

El compilador XSLT (xsltc.exe) compila hojas de estilo XSLT y genera un ensamblado. La hoja de estilos compilada se puede pasar directamente al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>. No se pueden generar ensamblados firmados con xsltc.exe.  
  
 La herramienta xsltc.exe está incluida en Visual Studio. Para obtener más información, consulte [Descargas de Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a>Argumento  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|`sourceFile`|Especifica el nombre de la hoja de estilos. La hoja de estilos debe ser un archivo local o bien estar ubicada en la intranet.|  
  
## <a name="options"></a>Opciones  
  
|Opción|Descripción|  
|------------|-----------------|  
|`/c[lass]:` `name`|Especifica el nombre de la clase para la hoja de estilos siguiente. El nombre de la clase puede ser completo.<br /><br /> De forma predeterminada, el nombre de la clase es igual al de la hoja de estilos. Por ejemplo, si se compila la hoja de estilos customer.xsl, el nombre predeterminado de la clase será customers.|  
|`/debug[`+&#124;-`]`|Especifica si se debe generar o no información de depuración.<br /><br /> Si se especifica la opción `+` o `/debug`, el compilador generará información de depuración y la almacenará en el archivo de base de datos del programa (PDB). El nombre del archivo PDB generado será `assemblyName`.pdb.<br /><br /> Si se especifica la opción `-`, que será la utilizada en caso de que no especifique `/debug`, no se generará información de depuración. Se genera un ensamblado listo para ser distribuido. **Nota:**  Si se compila en modo de depuración, es posible que ello afecte significativamente al rendimiento del XSLT.|  
|`/help`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|`/nologo`|Suprime el mensaje de copyright del compilador.|  
|`/platform:` `string`|Especifica las plataformas en las que se podrá ejecutar el ensamblado. A continuación se describen los valores permitidos para las plataformas:<br /><br /> `x86` compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.<br /><br /> `x64` compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.<br /><br /> Itanium compila el ensamblado de forma que Common Language Runtime de 64 bits pueda ejecutarlo en equipos que tengan un procesador Itanium.<br /><br /> `anycpu` compila en ensamblado de forma que se pueda ejecutar en cualquier plataforma. Este es el valor predeterminado.|  
|`/out:` `assemblyName`|Especifica el nombre del ensamblado que se va a generar. De forma predeterminada, el nombre del ensamblado es el mismo que el de la hoja de estilos, o bien de la primera hoja de estilos, en caso de existir varias.<br /><br /> Si la hoja de estilos contiene scripts, éstos se guardarán en un ensamblado aparte. Los nombres de los ensamblados de scripts se generarán a partir del nombre del ensamblado principal. Por ejemplo, si especificó que el nombre del ensamblado sería CustOrders.dll, el nombre del primer ensamblado de script será CustOrders_Script1.dll.|  
|`/settings:` `document+-, script+-, DTD+-,`|Especifica si se permiten o no funciones `document()`, scripts XSLT o definiciones de tipo de documento (DTD) en la hoja de estilos.<br /><br /> De forma predeterminada, no habrá compatibilidad con DTD, con las funciones `document()` y con los scripts.|  
|`@` `file`|Le permite especificar un archivo que contenga las opciones del compilador.|  
|`?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="remarks"></a>Comentarios  

 Las soluciones XSLT puede estar compuestas por múltiples módulos de hojas de estilos. La herramienta xsltc.exe genera ensamblados a partir de hojas de estilos. Dichos ensamblados se pueden pasar al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>. Esto puede ayudar a reducir los costos de implementación en ciertos escenarios de XSLT.  
  
> [!NOTE]
> Por otro lado, deberá incluir en su aplicación el ensamblado compilado como una referencia.  
  
 La herramienta xsltc.exe no valida los nombres de la clase (`/class:`*nombre*) o del ensamblado (`/out:`*nombreDelEnsamblado*). En caso de que estos nombres no sean válidos, el CLR se encargará de generar los errores correspondientes.  
  
## <a name="examples"></a>Ejemplos  

 La siguiente instrucción compila la hoja de estilos y crea un ensamblado llamado booksort.dll.  
  
```console  
xsltc booksort.xsl  
```  
  
 La siguiente instrucción compila la hoja de estilos, para después crear un ensamblado y un archivo PDB que se llaman booksort.dll y booksort.pdb, respectivamente.  
  
```console  
xsltc booksort.xsl /debug  
```  
  
 La instrucción siguiente compila una hoja de estilos que contiene un elemento msxsl:script y crea dos ensamblados, cuyos nombres son calc.dll y calc_Script1.dll.  
  
```console  
xsltc /settings:script+ calc.xsl  
```  
  
 La instrucción siguiente habilita el procesamiento DTD y el uso de scripts, para después crear dos ensamblados que se llamarán myTest.dll y myTest_Script1.dll.  
  
```console  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 La siguiente instrucción compila dos módulos de hoja de estilos y crea un único ensamblado llamado booksort.dll.  
  
```console  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Cómo: Realizar una transformación XSLT mediante un ensamblado](how-to-perform-an-xslt-transformation-by-using-an-assembly.md)
- [Transformaciones XSLT](xslt-transformations.md)
