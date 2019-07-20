---
title: Cadenas de conexión de ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 02fe8d984f1287673477bb142b3f9626e248898e
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363749"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="28e2a-102">Cadenas de conexión de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="28e2a-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="28e2a-103">Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28e2a-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="28e2a-104">El proveedor de datos recibe la cadena de conexión como el valor <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="28e2a-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="28e2a-105">El proveedor analiza la cadena de conexión y garantiza que la sintaxis es correcta y que se admiten las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="28e2a-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="28e2a-106">A continuación <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> , el método pasa los parámetros de conexión analizados al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28e2a-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="28e2a-107">El origen de datos realiza una validación adicional y establece una conexión.</span><span class="sxs-lookup"><span data-stu-id="28e2a-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="28e2a-108">Sintaxis de cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="28e2a-108">Connection string syntax</span></span>

<span data-ttu-id="28e2a-109">Una cadena de conexión es una lista delimitada por signos de punto y coma de pares de parámetros de clave-valor:</span><span class="sxs-lookup"><span data-stu-id="28e2a-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```
keyword1=value; keyword2=value;
```

<span data-ttu-id="28e2a-110">Las palabras clave no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="28e2a-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="28e2a-111">Sin embargo, los valores pueden distinguir entre mayúsculas y minúsculas, en función del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28e2a-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="28e2a-112">Las palabras clave y los valores pueden contener [caracteres de espacio en blanco](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="28e2a-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="28e2a-113">Los espacios en blanco iniciales y finales se omiten en las palabras clave y los valores sin comillas.</span><span class="sxs-lookup"><span data-stu-id="28e2a-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="28e2a-114">Si un valor contiene el punto y coma, [caracteres de control Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters)o espacios en blanco iniciales o finales, debe incluirse entre comillas simples o dobles.</span><span class="sxs-lookup"><span data-stu-id="28e2a-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="28e2a-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="28e2a-115">For example:</span></span>

```
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="28e2a-116">Es posible que el carácter envolvente no se encuentre dentro del valor que contiene.</span><span class="sxs-lookup"><span data-stu-id="28e2a-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="28e2a-117">Por lo tanto, un valor que contenga comillas simples solo se puede incluir entre comillas dobles y viceversa:</span><span class="sxs-lookup"><span data-stu-id="28e2a-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="28e2a-118">También puede escapar el carácter envolvente con dos de ellos juntos:</span><span class="sxs-lookup"><span data-stu-id="28e2a-118">You can also escape the enclosing character by using two of them together:</span></span>

```
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="28e2a-119">Las comillas, así como el signo igual, no requieren caracteres de escape, por lo que las siguientes cadenas de conexión son válidas:</span><span class="sxs-lookup"><span data-stu-id="28e2a-119">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="28e2a-120">Puesto que cada valor se lee hasta el punto y coma siguiente o el final de la cadena, el valor del último `a=b=c`ejemplo es y el punto y coma final es opcional.</span><span class="sxs-lookup"><span data-stu-id="28e2a-120">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="28e2a-121">Todas las cadenas de conexión comparten la misma sintaxis básica que se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e2a-121">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="28e2a-122">Sin embargo, el conjunto de palabras clave reconocidas depende del proveedor y ha evolucionado a lo largo de los años desde API anteriores, como *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="28e2a-122">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="28e2a-123">El proveedor de datos de *.NET Framework* para`SqlClient` *SQL Server* () admite muchas palabras clave de API anteriores, pero suele ser más flexible y acepta sinónimos para muchas de las palabras clave de cadena de conexión comunes.</span><span class="sxs-lookup"><span data-stu-id="28e2a-123">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="28e2a-124">Los errores tipográficos pueden producir errores.</span><span class="sxs-lookup"><span data-stu-id="28e2a-124">Typing mistakes can cause errors.</span></span> <span data-ttu-id="28e2a-125">Por ejemplo, `Integrated Security=true` es válido, pero `IntegratedSecurity=true` produce un error.</span><span class="sxs-lookup"><span data-stu-id="28e2a-125">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="28e2a-126">Las cadenas de conexión construidas manualmente en tiempo de ejecución desde la entrada de usuario no validada son vulnerables a ataques de inyección de cadenas y ponen en peligro la seguridad en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28e2a-126">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="28e2a-127">Para solucionar estos problemas, *ADO.NET* 2,0 presentó [generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md) para cada proveedor de datos *.NET Framework* .</span><span class="sxs-lookup"><span data-stu-id="28e2a-127">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](../../../../docs/framework/data/adonet/connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="28e2a-128">Estos generadores de cadenas de conexión exponen parámetros como propiedades fuertemente tipadas y permiten validar la cadena de conexión antes de enviarla al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28e2a-128">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="28e2a-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="28e2a-129">In This Section</span></span>

<span data-ttu-id="28e2a-130">[Generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="28e2a-130">[Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md)</span></span>\
<span data-ttu-id="28e2a-131">Muestra cómo usar las clases `ConnectionStringBuilder` para construir cadenas de conexión válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="28e2a-131">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="28e2a-132">[Cadenas de conexión y archivos de configuración](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="28e2a-132">[Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="28e2a-133">Muestra cómo almacenar y recuperar cadenas de conexión en archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="28e2a-133">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="28e2a-134">[Sintaxis de cadena de conexión](../../../../docs/framework/data/adonet/connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="28e2a-134">[Connection String Syntax](../../../../docs/framework/data/adonet/connection-string-syntax.md)</span></span>\
<span data-ttu-id="28e2a-135">Describe cómo configurar cadenas de conexión específicas de proveedor para `SqlClient`, `OracleClient`, `OleDb` y `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="28e2a-135">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="28e2a-136">[Protección de la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="28e2a-136">[Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md)</span></span>\
<span data-ttu-id="28e2a-137">Muestra técnicas de protección de la información utilizada para conectarse a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28e2a-137">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="28e2a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="28e2a-138">See also</span></span>

- [<span data-ttu-id="28e2a-139">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="28e2a-139">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="28e2a-140">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="28e2a-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
