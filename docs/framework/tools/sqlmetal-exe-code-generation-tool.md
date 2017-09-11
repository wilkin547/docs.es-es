---
title: "SqlMetal.exe (Herramienta de generación de código)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
caps.latest.revision: 43
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6d0ac9c682c60db8eb9e5188a71916dc5d97de60
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="57bac-102">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="57bac-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="57bac-103">La herramienta de la línea de comandos SqlMetal genera el código y las asignaciones del componente [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57bac-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="57bac-104">Si aplica las opciones que se incluyen posteriormente en este tema, puede indicarle a SqlMetal que realice algunas acciones diferentes, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="57bac-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
-   <span data-ttu-id="57bac-105">A partir de una base de datos, generar código fuente y atributos de asignación o un archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="57bac-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
-   <span data-ttu-id="57bac-106">A partir de una base de datos, generar un archivo de lenguaje intermedio de marcado de base de datos (.dbml) para su personalización.</span><span class="sxs-lookup"><span data-stu-id="57bac-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
-   <span data-ttu-id="57bac-107">A partir de un archivo .dbml, generar código y atributos de asignación o un archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="57bac-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="57bac-108">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="57bac-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="57bac-109">De manera predeterminada, el archivo se encuentra en `drive`:\Archivos de programa\Microsoft SDKs\Windows\\v`n.nn`\bin.</span><span class="sxs-lookup"><span data-stu-id="57bac-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="57bac-110">Si no instala Visual Studio, también puede obtener el archivo de SQLMetal descargando [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="57bac-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57bac-111">Los programadores que utilizan Visual Studio también pueden usar [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] para generar clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="57bac-111">Developers who use Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] to generate entity classes.</span></span> <span data-ttu-id="57bac-112">El enfoque de la línea de comandos se ajusta bien a las bases de datos grandes.</span><span class="sxs-lookup"><span data-stu-id="57bac-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="57bac-113">Dado que SqlMetal es una herramienta de línea de comandos, puede utilizarse en un proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="57bac-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="57bac-114">Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores (o el Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="57bac-114">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="57bac-115">Para obtener más información, vea [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md). En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57bac-115">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57bac-116">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57bac-116">Syntax</span></span>  
  
```  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="57bac-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="57bac-117">Options</span></span>  
 <span data-ttu-id="57bac-118">Para ver la lista de opciones más reciente, escriba `sqlmetal /?` en el símbolo del sistema de la ubicación de instalación.</span><span class="sxs-lookup"><span data-stu-id="57bac-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="57bac-119">**Opciones de conexión**</span><span class="sxs-lookup"><span data-stu-id="57bac-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="57bac-120">Opción</span><span class="sxs-lookup"><span data-stu-id="57bac-120">Option</span></span>|<span data-ttu-id="57bac-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bac-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="57bac-122">**/server:** *\<nombre>*</span><span class="sxs-lookup"><span data-stu-id="57bac-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="57bac-123">Especifica el nombre del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="57bac-124">**/database:** *\<nombre>*</span><span class="sxs-lookup"><span data-stu-id="57bac-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="57bac-125">Especifica el catálogo de base de datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="57bac-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="57bac-126">**/user:** *\<nombre>*</span><span class="sxs-lookup"><span data-stu-id="57bac-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="57bac-127">Especifica el identificador de usuario de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="57bac-127">Specifies logon user id.</span></span> <span data-ttu-id="57bac-128">Valor predeterminado: Usar autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="57bac-128">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="57bac-129">**/password:** *\<contraseña>*</span><span class="sxs-lookup"><span data-stu-id="57bac-129">**/password:** *\<password>*</span></span>|<span data-ttu-id="57bac-130">Especifica la contraseña de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="57bac-130">Specifies logon password.</span></span> <span data-ttu-id="57bac-131">Valor predeterminado: Usar autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="57bac-131">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="57bac-132">**/conn:** *\<cadena de conexión>*</span><span class="sxs-lookup"><span data-stu-id="57bac-132">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="57bac-133">Especifica la cadena de conexión a bases de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-133">Specifies database connection string.</span></span> <span data-ttu-id="57bac-134">No se puede usar con las opciones **/server**, **/database**, **/user**ni **/password** .</span><span class="sxs-lookup"><span data-stu-id="57bac-134">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="57bac-135">No incluya el nombre de archivo en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="57bac-135">Do not include the file name in the connection string.</span></span> <span data-ttu-id="57bac-136">En su lugar, agregue el nombre a la línea de comandos como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="57bac-136">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="57bac-137">Por ejemplo, en la línea siguiente se especifica "c:\northwnd.mdf" como archivo de entrada: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="57bac-137">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="57bac-138">**/timeout:** *\<segundos>*</span><span class="sxs-lookup"><span data-stu-id="57bac-138">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="57bac-139">Especifica el valor de tiempo de espera cuando SqlMetal tiene acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-139">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="57bac-140">Valor predeterminado: 0 (es decir, sin límite de tiempo).</span><span class="sxs-lookup"><span data-stu-id="57bac-140">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="57bac-141">**Opciones de extracción**</span><span class="sxs-lookup"><span data-stu-id="57bac-141">**Extraction options**</span></span>  
  
|<span data-ttu-id="57bac-142">Opción</span><span class="sxs-lookup"><span data-stu-id="57bac-142">Option</span></span>|<span data-ttu-id="57bac-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bac-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="57bac-144">**/views**</span><span class="sxs-lookup"><span data-stu-id="57bac-144">**/views**</span></span>|<span data-ttu-id="57bac-145">Extrae las vistas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-145">Extracts database views.</span></span>|  
|<span data-ttu-id="57bac-146">**/functions**</span><span class="sxs-lookup"><span data-stu-id="57bac-146">**/functions**</span></span>|<span data-ttu-id="57bac-147">Extrae las funciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-147">Extracts database functions.</span></span>|  
|<span data-ttu-id="57bac-148">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="57bac-148">**/sprocs**</span></span>|<span data-ttu-id="57bac-149">Extrae los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="57bac-149">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="57bac-150">**Opciones de salida**</span><span class="sxs-lookup"><span data-stu-id="57bac-150">**Output options**</span></span>  
  
|<span data-ttu-id="57bac-151">Opción</span><span class="sxs-lookup"><span data-stu-id="57bac-151">Option</span></span>|<span data-ttu-id="57bac-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bac-152">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="57bac-153">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="57bac-153">**/dbml** *[:file]*</span></span>|<span data-ttu-id="57bac-154">Envía el resultado como .dbml.</span><span class="sxs-lookup"><span data-stu-id="57bac-154">Sends output as .dbml.</span></span> <span data-ttu-id="57bac-155">No se puede usar con la opción **/map** .</span><span class="sxs-lookup"><span data-stu-id="57bac-155">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="57bac-156">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="57bac-156">**/code** *[:file]*</span></span>|<span data-ttu-id="57bac-157">Envía el resultado como código fuente.</span><span class="sxs-lookup"><span data-stu-id="57bac-157">Sends output as source code.</span></span> <span data-ttu-id="57bac-158">No se puede usar con la opción **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="57bac-158">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="57bac-159">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="57bac-159">**/map** *[:file]*</span></span>|<span data-ttu-id="57bac-160">Genera un archivo de asignación XML en lugar de atributos de asignación.</span><span class="sxs-lookup"><span data-stu-id="57bac-160">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="57bac-161">No se puede usar con la opción **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="57bac-161">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="57bac-162">**Varios**</span><span class="sxs-lookup"><span data-stu-id="57bac-162">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="57bac-163">Opción</span><span class="sxs-lookup"><span data-stu-id="57bac-163">Option</span></span>|<span data-ttu-id="57bac-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bac-164">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="57bac-165">**/language:** *\<lenguaje>*</span><span class="sxs-lookup"><span data-stu-id="57bac-165">**/language:** *\<language>*</span></span>|<span data-ttu-id="57bac-166">Especifica el lenguaje del código fuente.</span><span class="sxs-lookup"><span data-stu-id="57bac-166">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="57bac-167">*\<Lenguaje>* válido: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="57bac-167">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="57bac-168">Valor predeterminado: se deriva de la extensión del nombre del archivo de código.</span><span class="sxs-lookup"><span data-stu-id="57bac-168">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="57bac-169">**/namespace:** *\<nombre>*</span><span class="sxs-lookup"><span data-stu-id="57bac-169">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="57bac-170">Especifica el espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="57bac-170">Specifies namespace of the generated code.</span></span> <span data-ttu-id="57bac-171">Valor predeterminado: sin espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="57bac-171">Default value: no namespace.</span></span>|  
|<span data-ttu-id="57bac-172">**/context:** *\<tipo>*</span><span class="sxs-lookup"><span data-stu-id="57bac-172">**/context:** *\<type>*</span></span>|<span data-ttu-id="57bac-173">Especifica el nombre de la clase de contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-173">Specifies name of data context class.</span></span> <span data-ttu-id="57bac-174">Valor predeterminado: se deriva del nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-174">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="57bac-175">**/entitybase:** *\<tipo>*</span><span class="sxs-lookup"><span data-stu-id="57bac-175">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="57bac-176">Especifica la clase base de las clases de entidad en el código generado.</span><span class="sxs-lookup"><span data-stu-id="57bac-176">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="57bac-177">Valor predeterminado: entidades que no tienen clase base.</span><span class="sxs-lookup"><span data-stu-id="57bac-177">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="57bac-178">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="57bac-178">**/pluralize**</span></span>|<span data-ttu-id="57bac-179">Pone automáticamente en singular o en plural nombres de clases y miembros.</span><span class="sxs-lookup"><span data-stu-id="57bac-179">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="57bac-180">Esta opción solo está disponible en Estados Unidos. Versión en inglés.</span><span class="sxs-lookup"><span data-stu-id="57bac-180">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="57bac-181">**/serialization:** *\<opción>*</span><span class="sxs-lookup"><span data-stu-id="57bac-181">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="57bac-182">Genera las clases serializables.</span><span class="sxs-lookup"><span data-stu-id="57bac-182">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="57bac-183">*\<Opción>* válida: ninguna, unidireccional.</span><span class="sxs-lookup"><span data-stu-id="57bac-183">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="57bac-184">Valor predeterminado: None.</span><span class="sxs-lookup"><span data-stu-id="57bac-184">Default value: None.</span></span><br /><br /> <span data-ttu-id="57bac-185">Para obtener más información, vea [Serialización](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="57bac-185">For more information, see [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="57bac-186">**Archivo de entrada**</span><span class="sxs-lookup"><span data-stu-id="57bac-186">**Input File**</span></span>  
  
|<span data-ttu-id="57bac-187">Opción</span><span class="sxs-lookup"><span data-stu-id="57bac-187">Option</span></span>|<span data-ttu-id="57bac-188">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bac-188">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="57bac-189">**\<archivo de entrada>**</span><span class="sxs-lookup"><span data-stu-id="57bac-189">**\<input file>**</span></span>|<span data-ttu-id="57bac-190">Especifica un archivo .mdf de SQL Server Express, un archivo .sdf de [!INCLUDE[ssEW](../../../includes/ssew-md.md)] o un archivo intermedio .dbml.</span><span class="sxs-lookup"><span data-stu-id="57bac-190">Specifies a SQL Server Express .mdf file, a [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57bac-191">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57bac-191">Remarks</span></span>  
 <span data-ttu-id="57bac-192">La funcionalidad de SqlMetal se compone en realidad de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="57bac-192">SqlMetal functionality actually involves two steps:</span></span>  
  
-   <span data-ttu-id="57bac-193">La extracción de los metadatos de la base de datos en un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="57bac-193">Extracting the metadata of the database into a .dbml file.</span></span>  
  
-   <span data-ttu-id="57bac-194">La compilación de un archivo de salida de código.</span><span class="sxs-lookup"><span data-stu-id="57bac-194">Generating a code output file.</span></span>  
  
     <span data-ttu-id="57bac-195">Mediante las opciones apropiadas de la línea de comandos, puede generar código fuente de [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o de C# o puede generar un archivo de asignación XML.</span><span class="sxs-lookup"><span data-stu-id="57bac-195">By using the appropriate command-line options, you can produce [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="57bac-196">Para extraer los metadatos de un archivo .mdf, debe especificar el nombre del archivo .mdf después del resto de opciones.</span><span class="sxs-lookup"><span data-stu-id="57bac-196">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="57bac-197">Si no hay ningún **/server** especificado, se tomará **localhost/sqlexpress** .</span><span class="sxs-lookup"><span data-stu-id="57bac-197">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 [!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)]<span data-ttu-id="57bac-198"> produce una excepción si se cumple una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="57bac-198"> throws an exception if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="57bac-199">SqlMetal intenta extraer un procedimiento almacenado que se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="57bac-199">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
-   <span data-ttu-id="57bac-200">El nivel de anidamiento de una vista, función o procedimiento almacenado supera el nivel 32.</span><span class="sxs-lookup"><span data-stu-id="57bac-200">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="57bac-201">SqlMetal detecta esta excepción y la notifica como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="57bac-201">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="57bac-202">Para especificar un nombre de archivo de entrada, agregue el nombre a la línea de comandos como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="57bac-202">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="57bac-203">No se admite la inclusión del nombre de archivo en la cadena de conexión (mediante la opción **/conn** ).</span><span class="sxs-lookup"><span data-stu-id="57bac-203">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="57bac-204">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="57bac-204">Examples</span></span>  
 <span data-ttu-id="57bac-205">Generar un archivo .dbml que incluya los metadatos de SQL extraídos:</span><span class="sxs-lookup"><span data-stu-id="57bac-205">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="57bac-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="57bac-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="57bac-207">Generar un archivo .dbml que incluya los metadatos de SQL extraídos de un archivo .mdf mediante SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="57bac-207">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="57bac-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="57bac-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="57bac-209">Generar un archivo .dbml que incluya los metadatos de SQL extraídos de SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="57bac-209">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="57bac-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="57bac-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="57bac-211">Generar el código fuente de un archivo de metadatos .dbml:</span><span class="sxs-lookup"><span data-stu-id="57bac-211">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="57bac-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="57bac-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="57bac-213">Generar código fuente directamente a partir de los metadatos de SQL:</span><span class="sxs-lookup"><span data-stu-id="57bac-213">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="57bac-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="57bac-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57bac-215">Si usa la opción **/pluralize** con la base de datos de ejemplo Northwind, tenga en cuenta el comportamiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="57bac-215">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="57bac-216">Cuando SqlMetal genera nombres de tipos de fila para las tablas, los nombres de la tabla están en singular.</span><span class="sxs-lookup"><span data-stu-id="57bac-216">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="57bac-217">Cuando crea las propiedades <xref:System.Data.Linq.DataContext> para las tablas, los nombres de la tabla están en plural.</span><span class="sxs-lookup"><span data-stu-id="57bac-217">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="57bac-218">Casualmente, las tablas de la base de datos de ejemplo Northwind ya están en plural.</span><span class="sxs-lookup"><span data-stu-id="57bac-218">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="57bac-219">Por tanto, no podrá ver este componente en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="57bac-219">Therefore, you do not see that part working.</span></span> <span data-ttu-id="57bac-220">Aunque es una práctica común asignar nombres a las tablas de bases de datos en singular, también es habitual que .NET asigne nombres en plural a las colecciones.</span><span class="sxs-lookup"><span data-stu-id="57bac-220">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57bac-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="57bac-221">See Also</span></span>  
 <span data-ttu-id="57bac-222">[Cómo: Generar el modelo de objetos en Visual Basic o C#](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md) </span><span class="sxs-lookup"><span data-stu-id="57bac-222">[How to: Generate the Object Model in Visual Basic or C#](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md) </span></span>  
 <span data-ttu-id="57bac-223">[Generación de código en LINQ to SQL](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md) </span><span class="sxs-lookup"><span data-stu-id="57bac-223">[Code Generation in LINQ to SQL](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md) </span></span>  
 [<span data-ttu-id="57bac-224">Asignación externa</span><span class="sxs-lookup"><span data-stu-id="57bac-224">External Mapping</span></span>](../../../docs/framework/data/adonet/sql/linq/external-mapping.md)

