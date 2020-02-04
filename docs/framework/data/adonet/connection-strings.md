---
title: Cadenas de conexión
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: cb0b2831a22f3fe51dd7c5bfbe51e72f266a0003
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980241"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="9e25e-102">Cadenas de conexión de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e25e-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="9e25e-103">Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9e25e-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="9e25e-104">El proveedor de datos recibe la cadena de conexión como el valor de la propiedad <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e25e-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="9e25e-105">El proveedor analiza la cadena de conexión y garantiza que la sintaxis es correcta y que se admiten las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="9e25e-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="9e25e-106">A continuación, el método <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> pasa los parámetros de conexión analizados al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9e25e-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="9e25e-107">El origen de datos realiza una validación adicional y establece una conexión.</span><span class="sxs-lookup"><span data-stu-id="9e25e-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="9e25e-108">Sintaxis de cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="9e25e-108">Connection string syntax</span></span>

<span data-ttu-id="9e25e-109">Una cadena de conexión es una lista delimitada por signos de punto y coma de pares de parámetros de clave-valor:</span><span class="sxs-lookup"><span data-stu-id="9e25e-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```csharp
keyword1=value; keyword2=value;
```

<span data-ttu-id="9e25e-110">Las palabras clave no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9e25e-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="9e25e-111">Sin embargo, los valores pueden distinguir entre mayúsculas y minúsculas, en función del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9e25e-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="9e25e-112">Las palabras clave y los valores pueden contener [caracteres de espacio en blanco](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="9e25e-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="9e25e-113">Los espacios en blanco iniciales y finales se omiten en las palabras clave y los valores sin comillas.</span><span class="sxs-lookup"><span data-stu-id="9e25e-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="9e25e-114">Si un valor contiene el punto y coma, [caracteres de control Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters)o espacios en blanco iniciales o finales, debe incluirse entre comillas simples o dobles.</span><span class="sxs-lookup"><span data-stu-id="9e25e-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="9e25e-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e25e-115">For example:</span></span>

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="9e25e-116">Es posible que el carácter envolvente no se encuentre dentro del valor que contiene.</span><span class="sxs-lookup"><span data-stu-id="9e25e-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="9e25e-117">Por lo tanto, un valor que contenga comillas simples solo se puede incluir entre comillas dobles y viceversa:</span><span class="sxs-lookup"><span data-stu-id="9e25e-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="9e25e-118">También puede escapar el carácter envolvente con dos de ellos juntos:</span><span class="sxs-lookup"><span data-stu-id="9e25e-118">You can also escape the enclosing character by using two of them together:</span></span>

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="9e25e-119">Las comillas, así como el signo igual, no requieren caracteres de escape, por lo que las siguientes cadenas de conexión son válidas:</span><span class="sxs-lookup"><span data-stu-id="9e25e-119">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="9e25e-120">Puesto que cada valor se lee hasta el punto y coma siguiente o el final de la cadena, el valor del último ejemplo es `a=b=c`y el punto y coma final es opcional.</span><span class="sxs-lookup"><span data-stu-id="9e25e-120">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="9e25e-121">Todas las cadenas de conexión comparten la misma sintaxis básica que se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9e25e-121">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="9e25e-122">Sin embargo, el conjunto de palabras clave reconocidas depende del proveedor y ha evolucionado a lo largo de los años desde API anteriores, como *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="9e25e-122">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="9e25e-123">El proveedor de datos de *.NET Framework* para *SQL Server* (`SqlClient`) admite muchas palabras clave de API anteriores, pero suele ser más flexible y acepta sinónimos para muchas de las palabras clave de cadena de conexión comunes.</span><span class="sxs-lookup"><span data-stu-id="9e25e-123">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="9e25e-124">Los errores tipográficos pueden producir errores.</span><span class="sxs-lookup"><span data-stu-id="9e25e-124">Typing mistakes can cause errors.</span></span> <span data-ttu-id="9e25e-125">Por ejemplo, `Integrated Security=true` es válido, pero `IntegratedSecurity=true` produce un error.</span><span class="sxs-lookup"><span data-stu-id="9e25e-125">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="9e25e-126">Las cadenas de conexión construidas manualmente en tiempo de ejecución desde la entrada de usuario no validada son vulnerables a ataques de inyección de cadenas y ponen en peligro la seguridad en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9e25e-126">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="9e25e-127">Para solucionar estos problemas, *ADO.NET* 2,0 presentó [generadores de cadenas de conexión](connection-string-builders.md) para cada proveedor de datos *.NET Framework* .</span><span class="sxs-lookup"><span data-stu-id="9e25e-127">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="9e25e-128">Estos generadores de cadenas de conexión exponen parámetros como propiedades fuertemente tipadas y permiten validar la cadena de conexión antes de enviarla al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9e25e-128">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9e25e-129">Esta sección</span><span class="sxs-lookup"><span data-stu-id="9e25e-129">In This Section</span></span>

<span data-ttu-id="9e25e-130">[Generadores de cadenas de conexión](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="9e25e-130">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="9e25e-131">Muestra cómo usar las clases `ConnectionStringBuilder` para construir cadenas de conexión válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9e25e-131">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="9e25e-132">[Cadenas de conexión y archivos de configuración](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="9e25e-132">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="9e25e-133">Muestra cómo almacenar y recuperar cadenas de conexión en archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="9e25e-133">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="9e25e-134">\ de [Sintaxis de cadena de conexión](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="9e25e-134">[Connection String Syntax](connection-string-syntax.md)\</span></span>
<span data-ttu-id="9e25e-135">Describe cómo configurar cadenas de conexión específicas de proveedor para `SqlClient`, `OracleClient`, `OleDb` y `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="9e25e-135">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="9e25e-136">[Proteger la información de conexión](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="9e25e-136">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="9e25e-137">Muestra técnicas de protección de la información utilizada para conectarse a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9e25e-137">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e25e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e25e-138">See also</span></span>

- [<span data-ttu-id="9e25e-139">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="9e25e-139">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="9e25e-140">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e25e-140">ADO.NET Overview</span></span>](ado-net-overview.md)
