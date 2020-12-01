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
ms.openlocfilehash: 4edf11315892ed8267bee17d69a70033348eca5c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272571"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="672fe-104">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="672fe-104">SqlMetal.exe (Code Generation Tool)</span></span>

<span data-ttu-id="672fe-105">La herramienta de línea de comandos SqlMetal genera el código y las asignaciones del componente [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="672fe-105">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the .NET Framework.</span></span> <span data-ttu-id="672fe-106">Si aplica las opciones que se incluyen posteriormente en este tema, puede indicarle a SqlMetal que realice algunas acciones diferentes, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="672fe-106">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
- <span data-ttu-id="672fe-107">A partir de una base de datos, generar código fuente y atributos de asignación o un archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="672fe-107">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
- <span data-ttu-id="672fe-108">A partir de una base de datos, generar un archivo de lenguaje intermedio de marcado de base de datos (.dbml) para su personalización.</span><span class="sxs-lookup"><span data-stu-id="672fe-108">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
- <span data-ttu-id="672fe-109">A partir de un archivo .dbml, generar código y atributos de asignación o un archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="672fe-109">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="672fe-110">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="672fe-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="672fe-111">De manera predeterminada, el archivo se encuentra en `drive`:\Archivos de programa\Microsoft SDKs\Windows\\v`n.nn`\bin.</span><span class="sxs-lookup"><span data-stu-id="672fe-111">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="672fe-112">Si no instala Visual Studio, también puede obtener el archivo de SQLMetal descargando [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="672fe-112">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="672fe-113">Los desarrolladores que utilizan Visual Studio también pueden usar Object Relational Designer para generar clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="672fe-113">Developers who use Visual Studio can also use the Object Relational Designer to generate entity classes.</span></span> <span data-ttu-id="672fe-114">El enfoque de la línea de comandos se ajusta bien a las bases de datos grandes.</span><span class="sxs-lookup"><span data-stu-id="672fe-114">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="672fe-115">Dado que SqlMetal es una herramienta de línea de comandos, puede utilizarse en un proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="672fe-115">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="672fe-116">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="672fe-116">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="672fe-117">Para obtener más información, vea [Símbolos del sistema](developer-command-prompt-for-vs.md). En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="672fe-117">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="672fe-118">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="672fe-118">Syntax</span></span>  
  
```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="672fe-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="672fe-119">Options</span></span>  

 <span data-ttu-id="672fe-120">Para ver la lista de opciones más reciente, escriba `sqlmetal /?` en el símbolo del sistema de la ubicación de instalación.</span><span class="sxs-lookup"><span data-stu-id="672fe-120">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="672fe-121">**Opciones de conexión**</span><span class="sxs-lookup"><span data-stu-id="672fe-121">**Connection Options**</span></span>  
  
|<span data-ttu-id="672fe-122">Opción</span><span class="sxs-lookup"><span data-stu-id="672fe-122">Option</span></span>|<span data-ttu-id="672fe-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="672fe-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="672fe-124">**/server:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="672fe-124">**/server:** *\<name>*</span></span>|<span data-ttu-id="672fe-125">Especifica el nombre del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="672fe-125">Specifies database server name.</span></span>|  
|<span data-ttu-id="672fe-126">**/database:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="672fe-126">**/database:** *\<name>*</span></span>|<span data-ttu-id="672fe-127">Especifica el catálogo de base de datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="672fe-127">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="672fe-128">**/user:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="672fe-128">**/user:** *\<name>*</span></span>|<span data-ttu-id="672fe-129">Especifica el identificador de usuario de inicio de sesión. Valor predeterminado: Uso de la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="672fe-129">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="672fe-130">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="672fe-130">**/password:** *\<password>*</span></span>|<span data-ttu-id="672fe-131">Especifica la contraseña de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="672fe-131">Specifies logon password.</span></span> <span data-ttu-id="672fe-132">Valor predeterminado: Uso de la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="672fe-132">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="672fe-133">**/conn:** *\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="672fe-133">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="672fe-134">Especifica la cadena de conexión a bases de datos.</span><span class="sxs-lookup"><span data-stu-id="672fe-134">Specifies database connection string.</span></span> <span data-ttu-id="672fe-135">No se puede usar con las opciones **/server**, **/database**, **/user** ni **/password** .</span><span class="sxs-lookup"><span data-stu-id="672fe-135">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="672fe-136">No incluya el nombre de archivo en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="672fe-136">Do not include the file name in the connection string.</span></span> <span data-ttu-id="672fe-137">En su lugar, agregue el nombre a la línea de comandos como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="672fe-137">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="672fe-138">Por ejemplo, en la línea siguiente se especifica "c:\northwnd.mdf" como archivo de entrada: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** .</span><span class="sxs-lookup"><span data-stu-id="672fe-138">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="672fe-139">**/timeout:** *\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="672fe-139">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="672fe-140">Especifica el valor de tiempo de espera cuando SqlMetal tiene acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="672fe-140">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="672fe-141">Valor predeterminado: 0 (es decir, sin límite de tiempo).</span><span class="sxs-lookup"><span data-stu-id="672fe-141">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="672fe-142">**Opciones de extracción**</span><span class="sxs-lookup"><span data-stu-id="672fe-142">**Extraction options**</span></span>  
  
|<span data-ttu-id="672fe-143">Opción</span><span class="sxs-lookup"><span data-stu-id="672fe-143">Option</span></span>|<span data-ttu-id="672fe-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="672fe-144">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="672fe-145">**/views**</span><span class="sxs-lookup"><span data-stu-id="672fe-145">**/views**</span></span>|<span data-ttu-id="672fe-146">Extrae las vistas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="672fe-146">Extracts database views.</span></span>|  
|<span data-ttu-id="672fe-147">**/functions**</span><span class="sxs-lookup"><span data-stu-id="672fe-147">**/functions**</span></span>|<span data-ttu-id="672fe-148">Extrae las funciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="672fe-148">Extracts database functions.</span></span>|  
|<span data-ttu-id="672fe-149">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="672fe-149">**/sprocs**</span></span>|<span data-ttu-id="672fe-150">Extrae los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="672fe-150">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="672fe-151">**Opciones de salida**</span><span class="sxs-lookup"><span data-stu-id="672fe-151">**Output options**</span></span>  
  
|<span data-ttu-id="672fe-152">Opción</span><span class="sxs-lookup"><span data-stu-id="672fe-152">Option</span></span>|<span data-ttu-id="672fe-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="672fe-153">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="672fe-154">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="672fe-154">**/dbml** *[:file]*</span></span>|<span data-ttu-id="672fe-155">Envía el resultado como .dbml.</span><span class="sxs-lookup"><span data-stu-id="672fe-155">Sends output as .dbml.</span></span> <span data-ttu-id="672fe-156">No se puede usar con la opción **/map** .</span><span class="sxs-lookup"><span data-stu-id="672fe-156">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="672fe-157">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="672fe-157">**/code** *[:file]*</span></span>|<span data-ttu-id="672fe-158">Envía el resultado como código fuente.</span><span class="sxs-lookup"><span data-stu-id="672fe-158">Sends output as source code.</span></span> <span data-ttu-id="672fe-159">No se puede usar con la opción **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="672fe-159">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="672fe-160">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="672fe-160">**/map** *[:file]*</span></span>|<span data-ttu-id="672fe-161">Genera un archivo de asignación XML en lugar de atributos de asignación.</span><span class="sxs-lookup"><span data-stu-id="672fe-161">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="672fe-162">No se puede usar con la opción **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="672fe-162">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="672fe-163">**Varios**</span><span class="sxs-lookup"><span data-stu-id="672fe-163">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="672fe-164">Opción</span><span class="sxs-lookup"><span data-stu-id="672fe-164">Option</span></span>|<span data-ttu-id="672fe-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="672fe-165">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="672fe-166">**/language:** *\<language>*</span><span class="sxs-lookup"><span data-stu-id="672fe-166">**/language:** *\<language>*</span></span>|<span data-ttu-id="672fe-167">Especifica el lenguaje del código fuente.</span><span class="sxs-lookup"><span data-stu-id="672fe-167">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="672fe-168">*\<language>* válido: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="672fe-168">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="672fe-169">Valor predeterminado: Se deriva de la extensión del nombre del archivo de código.</span><span class="sxs-lookup"><span data-stu-id="672fe-169">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="672fe-170">**/namespace:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="672fe-170">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="672fe-171">Especifica el espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="672fe-171">Specifies namespace of the generated code.</span></span> <span data-ttu-id="672fe-172">Valor predeterminado: sin espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="672fe-172">Default value: no namespace.</span></span>|  
|<span data-ttu-id="672fe-173">**/context:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="672fe-173">**/context:** *\<type>*</span></span>|<span data-ttu-id="672fe-174">Especifica el nombre de la clase de contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="672fe-174">Specifies name of data context class.</span></span> <span data-ttu-id="672fe-175">Valor predeterminado: Se deriva del nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="672fe-175">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="672fe-176">**/entitybase:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="672fe-176">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="672fe-177">Especifica la clase base de las clases de entidad en el código generado.</span><span class="sxs-lookup"><span data-stu-id="672fe-177">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="672fe-178">Valor predeterminado: Entidades sin clase base.</span><span class="sxs-lookup"><span data-stu-id="672fe-178">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="672fe-179">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="672fe-179">**/pluralize**</span></span>|<span data-ttu-id="672fe-180">Pone automáticamente en singular o en plural nombres de clases y miembros.</span><span class="sxs-lookup"><span data-stu-id="672fe-180">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="672fe-181">Esta opción solo está disponible en Estados Unidos. Versión en inglés.</span><span class="sxs-lookup"><span data-stu-id="672fe-181">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="672fe-182">**/serialization:** *\<option>*</span><span class="sxs-lookup"><span data-stu-id="672fe-182">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="672fe-183">Genera las clases serializables.</span><span class="sxs-lookup"><span data-stu-id="672fe-183">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="672fe-184">*\<option>* válida: None, Unidirectional.</span><span class="sxs-lookup"><span data-stu-id="672fe-184">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="672fe-185">Valor predeterminado: Ninguno.</span><span class="sxs-lookup"><span data-stu-id="672fe-185">Default value: None.</span></span><br /><br /> <span data-ttu-id="672fe-186">Para obtener más información, vea [Serialización](../data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="672fe-186">For more information, see [Serialization](../data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="672fe-187">**Archivo de entrada**</span><span class="sxs-lookup"><span data-stu-id="672fe-187">**Input File**</span></span>  
  
|<span data-ttu-id="672fe-188">Opción</span><span class="sxs-lookup"><span data-stu-id="672fe-188">Option</span></span>|<span data-ttu-id="672fe-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="672fe-189">Description</span></span>|  
|------------|-----------------|  
|**\<input file>**|<span data-ttu-id="672fe-190">Especifica un archivo .mdf de SQL Server Express, un archivo .sdf de SQL Server Compact 3.5 o un archivo intermedio .dbml.</span><span class="sxs-lookup"><span data-stu-id="672fe-190">Specifies a SQL Server Express .mdf file, a SQL Server Compact 3.5 .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="672fe-191">Comentarios</span><span class="sxs-lookup"><span data-stu-id="672fe-191">Remarks</span></span>  

 <span data-ttu-id="672fe-192">La funcionalidad de SqlMetal se compone en realidad de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="672fe-192">SqlMetal functionality actually involves two steps:</span></span>  
  
- <span data-ttu-id="672fe-193">La extracción de los metadatos de la base de datos en un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="672fe-193">Extracting the metadata of the database into a .dbml file.</span></span>  
  
- <span data-ttu-id="672fe-194">La compilación de un archivo de salida de código.</span><span class="sxs-lookup"><span data-stu-id="672fe-194">Generating a code output file.</span></span>  
  
     <span data-ttu-id="672fe-195">Mediante las opciones apropiadas de la línea de comandos, puede generar código fuente de Visual Basic o de C# o puede generar un archivo de asignación XML.</span><span class="sxs-lookup"><span data-stu-id="672fe-195">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="672fe-196">Para extraer los metadatos de un archivo .mdf, debe especificar el nombre del archivo .mdf después del resto de opciones.</span><span class="sxs-lookup"><span data-stu-id="672fe-196">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="672fe-197">Si no hay ningún **/server** especificado, se tomará **localhost/sqlexpress** .</span><span class="sxs-lookup"><span data-stu-id="672fe-197">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="672fe-198">Microsoft SQL Server 2005 produce una excepción si se cumplen una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="672fe-198">Microsoft SQL Server 2005 throws an exception if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="672fe-199">SqlMetal intenta extraer un procedimiento almacenado que se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="672fe-199">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
- <span data-ttu-id="672fe-200">El nivel de anidamiento de una vista, función o procedimiento almacenado supera el nivel 32.</span><span class="sxs-lookup"><span data-stu-id="672fe-200">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="672fe-201">SqlMetal detecta esta excepción y la notifica como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="672fe-201">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="672fe-202">Para especificar un nombre de archivo de entrada, agregue el nombre a la línea de comandos como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="672fe-202">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="672fe-203">No se admite la inclusión del nombre de archivo en la cadena de conexión (mediante la opción **/conn** ).</span><span class="sxs-lookup"><span data-stu-id="672fe-203">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="672fe-204">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="672fe-204">Examples</span></span>  

 <span data-ttu-id="672fe-205">Generar un archivo .dbml que incluya los metadatos de SQL extraídos:</span><span class="sxs-lookup"><span data-stu-id="672fe-205">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="672fe-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="672fe-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="672fe-207">Generar un archivo .dbml que incluya los metadatos de SQL extraídos de un archivo .mdf mediante SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="672fe-207">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="672fe-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="672fe-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="672fe-209">Generar un archivo .dbml que incluya los metadatos de SQL extraídos de SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="672fe-209">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="672fe-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="672fe-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="672fe-211">Generar el código fuente de un archivo de metadatos .dbml:</span><span class="sxs-lookup"><span data-stu-id="672fe-211">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="672fe-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="672fe-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="672fe-213">Generar código fuente directamente a partir de los metadatos de SQL:</span><span class="sxs-lookup"><span data-stu-id="672fe-213">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="672fe-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="672fe-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
> <span data-ttu-id="672fe-215">Si usa la opción **/pluralize** con la base de datos de ejemplo Northwind, tenga en cuenta el comportamiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="672fe-215">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="672fe-216">Cuando SqlMetal genera nombres de tipos de fila para las tablas, los nombres de la tabla están en singular.</span><span class="sxs-lookup"><span data-stu-id="672fe-216">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="672fe-217">Cuando crea las propiedades <xref:System.Data.Linq.DataContext> para las tablas, los nombres de la tabla están en plural.</span><span class="sxs-lookup"><span data-stu-id="672fe-217">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="672fe-218">Casualmente, las tablas de la base de datos de ejemplo Northwind ya están en plural.</span><span class="sxs-lookup"><span data-stu-id="672fe-218">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="672fe-219">Por tanto, no podrá ver este componente en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="672fe-219">Therefore, you do not see that part working.</span></span> <span data-ttu-id="672fe-220">Aunque es una práctica común asignar nombres a las tablas de bases de datos en singular, también es habitual que .NET asigne nombres en plural a las colecciones.</span><span class="sxs-lookup"><span data-stu-id="672fe-220">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="672fe-221">Consulte también</span><span class="sxs-lookup"><span data-stu-id="672fe-221">See also</span></span>

- [<span data-ttu-id="672fe-222">Cómo: Generación del modelo de objetos en Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="672fe-222">How to: Generate the Object Model in Visual Basic or C#</span></span>](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [<span data-ttu-id="672fe-223">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="672fe-223">Code Generation in LINQ to SQL</span></span>](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="672fe-224">Asignación externa</span><span class="sxs-lookup"><span data-stu-id="672fe-224">External Mapping</span></span>](../data/adonet/sql/linq/external-mapping.md)
