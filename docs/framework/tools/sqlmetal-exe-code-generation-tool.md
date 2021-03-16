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
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="c3fd1-104">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="c3fd1-104">SqlMetal.exe (Code Generation Tool)</span></span>

<span data-ttu-id="c3fd1-105">La herramienta de línea de comandos SqlMetal genera el código y las asignaciones del componente [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-105">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the .NET Framework.</span></span> <span data-ttu-id="c3fd1-106">Si aplica las opciones que se incluyen posteriormente en este tema, puede indicarle a SqlMetal que realice algunas acciones diferentes, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-106">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
- <span data-ttu-id="c3fd1-107">A partir de una base de datos, generar código fuente y atributos de asignación o un archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-107">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
- <span data-ttu-id="c3fd1-108">A partir de una base de datos, generar un archivo de lenguaje intermedio de marcado de base de datos (.dbml) para su personalización.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-108">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
- <span data-ttu-id="c3fd1-109">A partir de un archivo .dbml, generar código y atributos de asignación o un archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-109">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
<span data-ttu-id="c3fd1-110">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c3fd1-111">De manera predeterminada, el archivo se encuentra en `drive`:\Archivos de programa\Microsoft SDKs\Windows\\v`n.nn`\bin.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-111">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="c3fd1-112">Si no instala Visual Studio, también puede obtener el archivo de SQLMetal descargando [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="c3fd1-112">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3fd1-113">Los desarrolladores que utilizan Visual Studio también pueden usar Object Relational Designer para generar clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-113">Developers who use Visual Studio can also use the Object Relational Designer to generate entity classes.</span></span> <span data-ttu-id="c3fd1-114">El enfoque de la línea de comandos se ajusta bien a las bases de datos grandes.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-114">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="c3fd1-115">Dado que SqlMetal es una herramienta de línea de comandos, puede utilizarse en un proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-115">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
<span data-ttu-id="c3fd1-116">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3fd1-116">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span> <span data-ttu-id="c3fd1-117">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-117">At the command prompt, enter the following command:</span></span>

```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="c3fd1-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="c3fd1-118">Options</span></span>  

 <span data-ttu-id="c3fd1-119">Para ver la lista de opciones más reciente, escriba `sqlmetal /?` en el símbolo del sistema de la ubicación de instalación.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-119">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="c3fd1-120">**Opciones de conexión**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-120">**Connection Options**</span></span>  
  
|<span data-ttu-id="c3fd1-121">Opción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-121">Option</span></span>|<span data-ttu-id="c3fd1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c3fd1-123">**/server:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-123">**/server:** *\<name>*</span></span>|<span data-ttu-id="c3fd1-124">Especifica el nombre del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-124">Specifies database server name.</span></span>|  
|<span data-ttu-id="c3fd1-125">**/database:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-125">**/database:** *\<name>*</span></span>|<span data-ttu-id="c3fd1-126">Especifica el catálogo de base de datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-126">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="c3fd1-127">**/user:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-127">**/user:** *\<name>*</span></span>|<span data-ttu-id="c3fd1-128">Especifica el identificador de usuario de inicio de sesión. Valor predeterminado: Uso de la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-128">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="c3fd1-129">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-129">**/password:** *\<password>*</span></span>|<span data-ttu-id="c3fd1-130">Especifica la contraseña de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-130">Specifies logon password.</span></span> <span data-ttu-id="c3fd1-131">Valor predeterminado: Uso de la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-131">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="c3fd1-132">**/conn:** *\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-132">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="c3fd1-133">Especifica la cadena de conexión a bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-133">Specifies database connection string.</span></span> <span data-ttu-id="c3fd1-134">No se puede usar con las opciones **/server**, **/database**, **/user** ni **/password** .</span><span class="sxs-lookup"><span data-stu-id="c3fd1-134">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="c3fd1-135">No incluya el nombre de archivo en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-135">Do not include the file name in the connection string.</span></span> <span data-ttu-id="c3fd1-136">En su lugar, agregue el nombre a la línea de comandos como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-136">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="c3fd1-137">Por ejemplo, en la línea siguiente se especifica "c:\northwnd.mdf" como archivo de entrada: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** .</span><span class="sxs-lookup"><span data-stu-id="c3fd1-137">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="c3fd1-138">**/timeout:** *\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-138">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="c3fd1-139">Especifica el valor de tiempo de espera cuando SqlMetal tiene acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-139">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="c3fd1-140">Valor predeterminado: 0 (es decir, sin límite de tiempo).</span><span class="sxs-lookup"><span data-stu-id="c3fd1-140">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="c3fd1-141">**Opciones de extracción**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-141">**Extraction options**</span></span>  
  
|<span data-ttu-id="c3fd1-142">Opción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-142">Option</span></span>|<span data-ttu-id="c3fd1-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c3fd1-144">**/views**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-144">**/views**</span></span>|<span data-ttu-id="c3fd1-145">Extrae las vistas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-145">Extracts database views.</span></span>|  
|<span data-ttu-id="c3fd1-146">**/functions**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-146">**/functions**</span></span>|<span data-ttu-id="c3fd1-147">Extrae las funciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-147">Extracts database functions.</span></span>|  
|<span data-ttu-id="c3fd1-148">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-148">**/sprocs**</span></span>|<span data-ttu-id="c3fd1-149">Extrae los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-149">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="c3fd1-150">**Opciones de salida**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-150">**Output options**</span></span>  
  
|<span data-ttu-id="c3fd1-151">Opción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-151">Option</span></span>|<span data-ttu-id="c3fd1-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-152">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c3fd1-153">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-153">**/dbml** *[:file]*</span></span>|<span data-ttu-id="c3fd1-154">Envía el resultado como .dbml.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-154">Sends output as .dbml.</span></span> <span data-ttu-id="c3fd1-155">No se puede usar con la opción **/map** .</span><span class="sxs-lookup"><span data-stu-id="c3fd1-155">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="c3fd1-156">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-156">**/code** *[:file]*</span></span>|<span data-ttu-id="c3fd1-157">Envía el resultado como código fuente.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-157">Sends output as source code.</span></span> <span data-ttu-id="c3fd1-158">No se puede usar con la opción **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="c3fd1-158">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="c3fd1-159">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-159">**/map** *[:file]*</span></span>|<span data-ttu-id="c3fd1-160">Genera un archivo de asignación XML en lugar de atributos de asignación.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-160">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="c3fd1-161">No se puede usar con la opción **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="c3fd1-161">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="c3fd1-162">**Varios**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-162">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="c3fd1-163">Opción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-163">Option</span></span>|<span data-ttu-id="c3fd1-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-164">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c3fd1-165">**/language:** *\<language>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-165">**/language:** *\<language>*</span></span>|<span data-ttu-id="c3fd1-166">Especifica el lenguaje del código fuente.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-166">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="c3fd1-167">*\<language>* válido: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-167">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="c3fd1-168">Valor predeterminado: Se deriva de la extensión del nombre del archivo de código.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-168">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="c3fd1-169">**/namespace:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-169">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="c3fd1-170">Especifica el espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-170">Specifies namespace of the generated code.</span></span> <span data-ttu-id="c3fd1-171">Valor predeterminado: sin espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-171">Default value: no namespace.</span></span>|  
|<span data-ttu-id="c3fd1-172">**/context:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-172">**/context:** *\<type>*</span></span>|<span data-ttu-id="c3fd1-173">Especifica el nombre de la clase de contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-173">Specifies name of data context class.</span></span> <span data-ttu-id="c3fd1-174">Valor predeterminado: Se deriva del nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-174">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="c3fd1-175">**/entitybase:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-175">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="c3fd1-176">Especifica la clase base de las clases de entidad en el código generado.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-176">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="c3fd1-177">Valor predeterminado: Entidades sin clase base.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-177">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="c3fd1-178">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-178">**/pluralize**</span></span>|<span data-ttu-id="c3fd1-179">Pone automáticamente en singular o en plural nombres de clases y miembros.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-179">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="c3fd1-180">Esta opción solo está disponible en Estados Unidos. Versión en inglés.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-180">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="c3fd1-181">**/serialization:** *\<option>*</span><span class="sxs-lookup"><span data-stu-id="c3fd1-181">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="c3fd1-182">Genera las clases serializables.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-182">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="c3fd1-183">*\<option>* válida: None, Unidirectional.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-183">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="c3fd1-184">Valor predeterminado: Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-184">Default value: None.</span></span><br /><br /> <span data-ttu-id="c3fd1-185">Para obtener más información, vea [Serialización](../data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="c3fd1-185">For more information, see [Serialization](../data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="c3fd1-186">**Archivo de entrada**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-186">**Input File**</span></span>  
  
|<span data-ttu-id="c3fd1-187">Opción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-187">Option</span></span>|<span data-ttu-id="c3fd1-188">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3fd1-188">Description</span></span>|  
|------------|-----------------|  
|**\<input file>**|<span data-ttu-id="c3fd1-189">Especifica un archivo .mdf de SQL Server Express, un archivo .sdf de SQL Server Compact 3.5 o un archivo intermedio .dbml.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-189">Specifies a SQL Server Express .mdf file, a SQL Server Compact 3.5 .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3fd1-190">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3fd1-190">Remarks</span></span>  

 <span data-ttu-id="c3fd1-191">La funcionalidad de SqlMetal se compone en realidad de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-191">SqlMetal functionality actually involves two steps:</span></span>  
  
- <span data-ttu-id="c3fd1-192">La extracción de los metadatos de la base de datos en un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-192">Extracting the metadata of the database into a .dbml file.</span></span>  
  
- <span data-ttu-id="c3fd1-193">La compilación de un archivo de salida de código.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-193">Generating a code output file.</span></span>  
  
     <span data-ttu-id="c3fd1-194">Mediante las opciones apropiadas de la línea de comandos, puede generar código fuente de Visual Basic o de C# o puede generar un archivo de asignación XML.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-194">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="c3fd1-195">Para extraer los metadatos de un archivo .mdf, debe especificar el nombre del archivo .mdf después del resto de opciones.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-195">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="c3fd1-196">Si no hay ningún **/server** especificado, se tomará **localhost/sqlexpress** .</span><span class="sxs-lookup"><span data-stu-id="c3fd1-196">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="c3fd1-197">Microsoft SQL Server 2005 produce una excepción si se cumplen una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-197">Microsoft SQL Server 2005 throws an exception if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="c3fd1-198">SqlMetal intenta extraer un procedimiento almacenado que se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-198">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
- <span data-ttu-id="c3fd1-199">El nivel de anidamiento de una vista, función o procedimiento almacenado supera el nivel 32.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-199">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="c3fd1-200">SqlMetal detecta esta excepción y la notifica como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-200">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="c3fd1-201">Para especificar un nombre de archivo de entrada, agregue el nombre a la línea de comandos como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-201">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="c3fd1-202">No se admite la inclusión del nombre de archivo en la cadena de conexión (mediante la opción **/conn** ).</span><span class="sxs-lookup"><span data-stu-id="c3fd1-202">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c3fd1-203">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c3fd1-203">Examples</span></span>  

 <span data-ttu-id="c3fd1-204">Generar un archivo .dbml que incluya los metadatos de SQL extraídos:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-204">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="c3fd1-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="c3fd1-206">Generar un archivo .dbml que incluya los metadatos de SQL extraídos de un archivo .mdf mediante SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-206">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="c3fd1-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="c3fd1-208">Generar un archivo .dbml que incluya los metadatos de SQL extraídos de SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-208">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="c3fd1-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="c3fd1-210">Generar el código fuente de un archivo de metadatos .dbml:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-210">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="c3fd1-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="c3fd1-212">Generar código fuente directamente a partir de los metadatos de SQL:</span><span class="sxs-lookup"><span data-stu-id="c3fd1-212">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="c3fd1-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="c3fd1-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3fd1-214">Si usa la opción **/pluralize** con la base de datos de ejemplo Northwind, tenga en cuenta el comportamiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-214">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="c3fd1-215">Cuando SqlMetal genera nombres de tipos de fila para las tablas, los nombres de la tabla están en singular.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-215">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="c3fd1-216">Cuando crea las propiedades <xref:System.Data.Linq.DataContext> para las tablas, los nombres de la tabla están en plural.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-216">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="c3fd1-217">Casualmente, las tablas de la base de datos de ejemplo Northwind ya están en plural.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-217">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="c3fd1-218">Por tanto, no podrá ver este componente en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-218">Therefore, you do not see that part working.</span></span> <span data-ttu-id="c3fd1-219">Aunque es una práctica común asignar nombres a las tablas de bases de datos en singular, también es habitual que .NET asigne nombres en plural a las colecciones.</span><span class="sxs-lookup"><span data-stu-id="c3fd1-219">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3fd1-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3fd1-220">See also</span></span>

- [<span data-ttu-id="c3fd1-221">Cómo: Generación del modelo de objetos en Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="c3fd1-221">How to: Generate the Object Model in Visual Basic or C#</span></span>](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [<span data-ttu-id="c3fd1-222">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c3fd1-222">Code Generation in LINQ to SQL</span></span>](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="c3fd1-223">Asignación externa</span><span class="sxs-lookup"><span data-stu-id="c3fd1-223">External Mapping</span></span>](../data/adonet/sql/linq/external-mapping.md)
