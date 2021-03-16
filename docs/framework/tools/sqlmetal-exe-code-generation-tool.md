---
title: SqlMetal.exe (Herramienta de generación de código)
description: Conozca SqlMetal.exe, la herramienta de generación de código. Use la herramienta para generar código y asignaciones para el componente LINQ to SQL de .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: b3d52e5ce070f1a86554a2c8b8cd581b2e4bc685
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258769"
---
# <a name="sqlmetalexe-code-generation-tool"></a>SqlMetal.exe (Herramienta de generación de código)

La herramienta de línea de comandos SqlMetal genera el código y las asignaciones del componente [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] de .NET Framework. Si aplica las opciones que se incluyen posteriormente en este tema, puede indicarle a SqlMetal que realice algunas acciones diferentes, entre las que se incluyen las siguientes:  
  
- A partir de una base de datos, generar código fuente y atributos de asignación o un archivo de asignación.  
  
- A partir de una base de datos, generar un archivo de lenguaje intermedio de marcado de base de datos (.dbml) para su personalización.  
  
- A partir de un archivo .dbml, generar código y atributos de asignación o un archivo de asignación.  
  
Esta herramienta se instala automáticamente con Visual Studio. De manera predeterminada, el archivo se encuentra en `drive`:\Archivos de programa\Microsoft SDKs\Windows\\v`n.nn`\bin. Si no instala Visual Studio, también puede obtener el archivo de SQLMetal descargando [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).  
  
> [!NOTE]
> Los desarrolladores que utilizan Visual Studio también pueden usar Object Relational Designer para generar clases de entidad. El enfoque de la línea de comandos se ajusta bien a las bases de datos grandes. Dado que SqlMetal es una herramienta de línea de comandos, puede utilizarse en un proceso de compilación.  
  
Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell). En el símbolo del sistema, escriba el siguiente comando:

```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a>Opciones  

 Para ver la lista de opciones más reciente, escriba `sqlmetal /?` en el símbolo del sistema de la ubicación de instalación.  
  
 **Opciones de conexión**  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/server:** *\<name>*|Especifica el nombre del servidor de bases de datos.|  
|**/database:** *\<name>*|Especifica el catálogo de base de datos del servidor.|  
|**/user:** *\<name>*|Especifica el identificador de usuario de inicio de sesión. Valor predeterminado: Uso de la autenticación de Windows.|  
|**/password:** *\<password>*|Especifica la contraseña de inicio de sesión. Valor predeterminado: Uso de la autenticación de Windows.|  
|**/conn:** *\<connection string>*|Especifica la cadena de conexión a bases de datos. No se puede usar con las opciones **/server**, **/database**, **/user** ni **/password** .<br /><br /> No incluya el nombre de archivo en la cadena de conexión. En su lugar, agregue el nombre a la línea de comandos como archivo de entrada. Por ejemplo, en la línea siguiente se especifica "c:\northwnd.mdf" como archivo de entrada: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** .|  
|**/timeout:** *\<seconds>*|Especifica el valor de tiempo de espera cuando SqlMetal tiene acceso a la base de datos. Valor predeterminado: 0 (es decir, sin límite de tiempo).|  
  
 **Opciones de extracción**  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/views**|Extrae las vistas de base de datos.|  
|**/functions**|Extrae las funciones de base de datos.|  
|**/sprocs**|Extrae los procedimientos almacenados.|  
  
 **Opciones de salida**  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/dbml** *[:file]*|Envía el resultado como .dbml. No se puede usar con la opción **/map** .|  
|**/code** *[:file]*|Envía el resultado como código fuente. No se puede usar con la opción **/dbml** .|  
|**/map** *[:file]*|Genera un archivo de asignación XML en lugar de atributos de asignación. No se puede usar con la opción **/dbml** .|  
  
 **Varios**  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/language:** *\<language>*|Especifica el lenguaje del código fuente.<br /><br /> *\<language>* válido: vb, csharp.<br /><br /> Valor predeterminado: Se deriva de la extensión del nombre del archivo de código.|  
|**/namespace:** *\<name>*|Especifica el espacio de nombres del código generado. Valor predeterminado: sin espacio de nombres.|  
|**/context:** *\<type>*|Especifica el nombre de la clase de contexto de datos. Valor predeterminado: Se deriva del nombre de la base de datos.|  
|**/entitybase:** *\<type>*|Especifica la clase base de las clases de entidad en el código generado. Valor predeterminado: Entidades sin clase base.|  
|**/pluralize**|Pone automáticamente en singular o en plural nombres de clases y miembros.<br /><br /> Esta opción solo está disponible en Estados Unidos. Versión en inglés.|  
|**/serialization:** *\<option>*|Genera las clases serializables.<br /><br /> *\<option>* válida: None, Unidirectional. Valor predeterminado: Ninguno.<br /><br /> Para obtener más información, vea [Serialización](../data/adonet/sql/linq/serialization.md).|  
  
 **Archivo de entrada**  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\<input file>**|Especifica un archivo .mdf de SQL Server Express, un archivo .sdf de SQL Server Compact 3.5 o un archivo intermedio .dbml.|  
  
## <a name="remarks"></a>Comentarios  

 La funcionalidad de SqlMetal se compone en realidad de dos pasos:  
  
- La extracción de los metadatos de la base de datos en un archivo .dbml.  
  
- La compilación de un archivo de salida de código.  
  
     Mediante las opciones apropiadas de la línea de comandos, puede generar código fuente de Visual Basic o de C# o puede generar un archivo de asignación XML.  
  
 Para extraer los metadatos de un archivo .mdf, debe especificar el nombre del archivo .mdf después del resto de opciones.  
  
 Si no hay ningún **/server** especificado, se tomará **localhost/sqlexpress** .  
  
 Microsoft SQL Server 2005 produce una excepción si se cumplen una o varias de las condiciones siguientes:  
  
- SqlMetal intenta extraer un procedimiento almacenado que se llama a sí mismo.  
  
- El nivel de anidamiento de una vista, función o procedimiento almacenado supera el nivel 32.  
  
     SqlMetal detecta esta excepción y la notifica como una advertencia.  
  
 Para especificar un nombre de archivo de entrada, agregue el nombre a la línea de comandos como archivo de entrada. No se admite la inclusión del nombre de archivo en la cadena de conexión (mediante la opción **/conn** ).  
  
## <a name="examples"></a>Ejemplos  

 Generar un archivo .dbml que incluya los metadatos de SQL extraídos:  
  
 **sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**  
  
 Generar un archivo .dbml que incluya los metadatos de SQL extraídos de un archivo .mdf mediante SQL Server Express:  
  
 **sqlmetal /dbml:mymeta.dbml mydbfile.mdf**  
  
 Generar un archivo .dbml que incluya los metadatos de SQL extraídos de SQL Server Express:  
  
 **sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**  
  
 Generar el código fuente de un archivo de metadatos .dbml:  
  
 **sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**  
  
 Generar código fuente directamente a partir de los metadatos de SQL:  
  
 **sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**  
  
> [!NOTE]
> Si usa la opción **/pluralize** con la base de datos de ejemplo Northwind, tenga en cuenta el comportamiento siguiente. Cuando SqlMetal genera nombres de tipos de fila para las tablas, los nombres de la tabla están en singular. Cuando crea las propiedades <xref:System.Data.Linq.DataContext> para las tablas, los nombres de la tabla están en plural. Casualmente, las tablas de la base de datos de ejemplo Northwind ya están en plural. Por tanto, no podrá ver este componente en funcionamiento. Aunque es una práctica común asignar nombres a las tablas de bases de datos en singular, también es habitual que .NET asigne nombres en plural a las colecciones.  
  
## <a name="see-also"></a>Consulte también

- [Cómo: Generación del modelo de objetos en Visual Basic o C#](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [Generación de código en LINQ to SQL](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Asignación externa](../data/adonet/sql/linq/external-mapping.md)
