---
title: "Cadenas de conexión de ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd787373b869c31727cfc0d027b6b98774b0d630
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="f40fd-102">Cadenas de conexión de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f40fd-102">Connection Strings in ADO.NET</span></span>
<span data-ttu-id="f40fd-103">.NET Framework 2.0 incorporó nuevas capacidades para trabajar con cadenas de conexión, incluida la introducción de nuevas palabras clave en las clases generadoras de cadenas de conexión, que facilitan la creación de cadenas de conexión válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f40fd-103">The .NET Framework 2.0 introduced new capabilities for working with connection strings, including the introduction of new keywords to the connection string builder classes, which facilitate creating valid connection strings at run time.</span></span>  
  
 <span data-ttu-id="f40fd-104">Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f40fd-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="f40fd-105">La sintaxis depende del proveedor de datos y la cadena de conexión se analiza mientras se intenta abrir una conexión.</span><span class="sxs-lookup"><span data-stu-id="f40fd-105">The syntax depends on the data provider, and the connection string is parsed during the attempt to open a connection.</span></span> <span data-ttu-id="f40fd-106">Los errores de sintaxis generan una excepción en tiempo de ejecución, pero otros errores solo se producen después de que el origen de datos recibe la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="f40fd-106">Syntax errors generate a run-time exception, but other errors occur only after the data source receives connection information.</span></span> <span data-ttu-id="f40fd-107">Una vez validada la cadena de conexión, el origen de datos aplica las opciones especificadas en ella y abre la conexión.</span><span class="sxs-lookup"><span data-stu-id="f40fd-107">Once validated, the data source applies the options specified in the connection string and opens the connection.</span></span>  
  
 <span data-ttu-id="f40fd-108">El formato de una cadena de conexión es una lista de pares de parámetros de clave y valor delimitados por punto y coma:</span><span class="sxs-lookup"><span data-stu-id="f40fd-108">The format of a connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>  
  
 `keyword1=value; keyword2=value;`  
  
 <span data-ttu-id="f40fd-109">Las palabras clave no distinguen entre mayúsculas y minúsculas y los espacios entre los pares clave-valor se omiten.</span><span class="sxs-lookup"><span data-stu-id="f40fd-109">Keywords are not case sensitive, and spaces between key/value pairs are ignored.</span></span> <span data-ttu-id="f40fd-110">Sin embargo, los valores pueden distinguir entre mayúsculas y minúsculas, en función del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f40fd-110">However, values may be case sensitive, depending on the data source.</span></span> <span data-ttu-id="f40fd-111">Los valores que contengan un punto y coma, caracteres de comilla sencilla o caracteres de comilla doble deben colocarse entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="f40fd-111">Any values containing a semicolon, single quotation marks, or double quotation marks must be enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="f40fd-112">La sintaxis válida de cadena de conexión depende del proveedor y ha evolucionado a lo largo de los años desde las primeras API como ODBC.</span><span class="sxs-lookup"><span data-stu-id="f40fd-112">Valid connection string syntax depends on the provider, and has evolved over the years from earlier APIs like ODBC.</span></span> <span data-ttu-id="f40fd-113">El proveedor de datos .NET Framework para SQL Server (SqlClient) incorpora muchos elementos de la sintaxis antigua y, por lo general, es más flexible con la sintaxis común de cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="f40fd-113">The .NET Framework Data Provider for SQL Server (SqlClient) incorporates many elements from older syntax and is generally more flexible with common connection string syntax.</span></span> <span data-ttu-id="f40fd-114">Con frecuencia existen sinónimos igualmente válidos para los elementos de sintaxis de la cadena de conexión, pero algunos errores de sintaxis y ortografía pueden generar problemas.</span><span class="sxs-lookup"><span data-stu-id="f40fd-114">There are frequently equally valid synonyms for connection string syntax elements, but some syntax and spelling errors can cause problems.</span></span> <span data-ttu-id="f40fd-115">Por ejemplo, "`Integrated Security=true`" es válido, en tanto que "`IntegratedSecurity=true`" genera un error.</span><span class="sxs-lookup"><span data-stu-id="f40fd-115">For example, "`Integrated Security=true`" is valid, whereas "`IntegratedSecurity=true`" causes an error.</span></span> <span data-ttu-id="f40fd-116">Además, las cadenas de conexión construidas en tiempo de ejecución a partir de entrada de usuario no validada pueden dar lugar a ataques de inyección de cadenas, lo que pone en peligro la seguridad en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f40fd-116">In addition, connection strings constructed at run time from unvalidated user input can lead to string injection attacks, jeopardizing security at the data source.</span></span>  
  
 <span data-ttu-id="f40fd-117">Para solucionar estos problemas, ADO.NET 2.0 incorporó nuevos generadores de cadenas de conexión para cada proveedor de datos .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f40fd-117">To address these problems, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="f40fd-118">Las palabras clave se exponen como propiedades, lo que permite validar la sintaxis de la cadena de conexión antes de su envío al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f40fd-118">Keywords are exposed as properties, enabling connection string syntax to be validated before submission to the data source.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f40fd-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f40fd-119">In This Section</span></span>  
 [<span data-ttu-id="f40fd-120">Generadores de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="f40fd-120">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="f40fd-121">Muestra cómo usar las clases `ConnectionStringBuilder` para construir cadenas de conexión válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f40fd-121">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>  
  
 [<span data-ttu-id="f40fd-122">Las cadenas de conexión y archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f40fd-122">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="f40fd-123">Muestra cómo almacenar y recuperar cadenas de conexión en archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="f40fd-123">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>  
  
 [<span data-ttu-id="f40fd-124">Sintaxis de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="f40fd-124">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="f40fd-125">Describe cómo configurar cadenas de conexión específicas de proveedor para `SqlClient`, `OracleClient`, `OleDb` y `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="f40fd-125">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>  
  
 [<span data-ttu-id="f40fd-126">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="f40fd-126">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="f40fd-127">Muestra técnicas de protección de la información utilizada para conectarse a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f40fd-127">Demonstrates techniques for protecting information used to connect to a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f40fd-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f40fd-128">See Also</span></span>  
 [<span data-ttu-id="f40fd-129">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="f40fd-129">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="f40fd-130">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f40fd-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
