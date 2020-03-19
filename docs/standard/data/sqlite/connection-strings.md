---
title: Cadenas de conexión
ms.date: 12/13/2019
description: Las palabras clave admitidas y los valores de las cadenas de conexión.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401200"
---
# <a name="connection-strings"></a><span data-ttu-id="c1aff-103">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="c1aff-103">Connection strings</span></span>

<span data-ttu-id="c1aff-104">Se utiliza una cadena de conexión para especificar cómo conectarse a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1aff-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="c1aff-105">Las cadenas de conexión de Microsoft.Data.Sqlite siguen la [sintaxis estándar de ADO.NET](../../../framework/data/adonet/connection-strings.md) como una lista separada por punto y coma de palabras clave y valores.</span><span class="sxs-lookup"><span data-stu-id="c1aff-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="c1aff-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c1aff-106">Keywords</span></span>

<span data-ttu-id="c1aff-107">Las siguientes palabras clave de cadena de conexión se pueden utilizar con Microsoft.Data.Sqlite:</span><span class="sxs-lookup"><span data-stu-id="c1aff-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="c1aff-108">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="c1aff-108">Data source</span></span>

<span data-ttu-id="c1aff-109">Ruta de acceso al archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1aff-109">The path to the database file.</span></span> <span data-ttu-id="c1aff-110">*DataSource* (sin espacio) y *Filename* son alias de esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="c1aff-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="c1aff-111">SQLite trata las rutas de acceso relativas al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="c1aff-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="c1aff-112">También se pueden especificar rutas absolutas.</span><span class="sxs-lookup"><span data-stu-id="c1aff-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="c1aff-113">Si **está vacío**, SQLite crea una base de datos temporal en disco que se elimina cuando se cierra la conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="c1aff-114">Si `:memory:`, se utiliza una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c1aff-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="c1aff-115">Para obtener más información, consulte [Bases de datos en memoria](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="c1aff-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="c1aff-116">Las rutas de `|DataDirectory|` acceso que comienzan con la cadena de sustitución se tratan igual que las rutas relativas.</span><span class="sxs-lookup"><span data-stu-id="c1aff-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="c1aff-117">Si se establece, las rutas de acceso se realizan en relación con el valor de propiedad de dominio de aplicación DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="c1aff-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="c1aff-118">Esta palabra clave también admite [nombres de archivo URI](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="c1aff-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="c1aff-119">Mode</span><span class="sxs-lookup"><span data-stu-id="c1aff-119">Mode</span></span>

<span data-ttu-id="c1aff-120">El modo de conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-120">The connection mode.</span></span>

| <span data-ttu-id="c1aff-121">Value</span><span class="sxs-lookup"><span data-stu-id="c1aff-121">Value</span></span>           | <span data-ttu-id="c1aff-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1aff-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c1aff-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="c1aff-123">ReadWriteCreate</span></span> | <span data-ttu-id="c1aff-124">Abre la base de datos para leerla y escribirla y la crea si no existe.</span><span class="sxs-lookup"><span data-stu-id="c1aff-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="c1aff-125">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1aff-125">This is the default.</span></span> |
| <span data-ttu-id="c1aff-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c1aff-126">ReadWrite</span></span>       | <span data-ttu-id="c1aff-127">Abre la base de datos para leer y escribir.</span><span class="sxs-lookup"><span data-stu-id="c1aff-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="c1aff-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="c1aff-128">ReadOnly</span></span>        | <span data-ttu-id="c1aff-129">Abre la base de datos en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c1aff-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="c1aff-130">Memoria</span><span class="sxs-lookup"><span data-stu-id="c1aff-130">Memory</span></span>          | <span data-ttu-id="c1aff-131">Abre una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c1aff-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="c1aff-132">Cache</span><span class="sxs-lookup"><span data-stu-id="c1aff-132">Cache</span></span>

<span data-ttu-id="c1aff-133">El modo de almacenamiento en caché utilizado por la conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="c1aff-134">Value</span><span class="sxs-lookup"><span data-stu-id="c1aff-134">Value</span></span>   | <span data-ttu-id="c1aff-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1aff-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c1aff-136">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c1aff-136">Default</span></span> | <span data-ttu-id="c1aff-137">Utiliza el modo predeterminado de la biblioteca SQLite subyacente.</span><span class="sxs-lookup"><span data-stu-id="c1aff-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="c1aff-138">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1aff-138">This is the default.</span></span>                   |
| <span data-ttu-id="c1aff-139">Privada</span><span class="sxs-lookup"><span data-stu-id="c1aff-139">Private</span></span> | <span data-ttu-id="c1aff-140">Cada conexión utiliza una memoria caché privada.</span><span class="sxs-lookup"><span data-stu-id="c1aff-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="c1aff-141">Compartido</span><span class="sxs-lookup"><span data-stu-id="c1aff-141">Shared</span></span>  | <span data-ttu-id="c1aff-142">Las conexiones comparten una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="c1aff-142">Connections share a cache.</span></span> <span data-ttu-id="c1aff-143">Este modo puede cambiar el comportamiento del bloqueo de transacciones y tablas.</span><span class="sxs-lookup"><span data-stu-id="c1aff-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="c1aff-144">Contraseña</span><span class="sxs-lookup"><span data-stu-id="c1aff-144">Password</span></span>

<span data-ttu-id="c1aff-145">La clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="c1aff-145">The encryption key.</span></span> <span data-ttu-id="c1aff-146">Cuando se `PRAGMA key` especifica, se envía inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="c1aff-147">La contraseña no tiene ningún efecto cuando la biblioteca SQLite nativa no admite el cifrado.</span><span class="sxs-lookup"><span data-stu-id="c1aff-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="c1aff-148">Claves externas</span><span class="sxs-lookup"><span data-stu-id="c1aff-148">Foreign Keys</span></span>

<span data-ttu-id="c1aff-149">Valor que indica si se deben habilitar las restricciones de clave externa.</span><span class="sxs-lookup"><span data-stu-id="c1aff-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="c1aff-150">Value</span><span class="sxs-lookup"><span data-stu-id="c1aff-150">Value</span></span>   | <span data-ttu-id="c1aff-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1aff-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="c1aff-152">True</span><span class="sxs-lookup"><span data-stu-id="c1aff-152">True</span></span>    | <span data-ttu-id="c1aff-153">Envía `PRAGMA foreign_keys = 1` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="c1aff-154">False</span><span class="sxs-lookup"><span data-stu-id="c1aff-154">False</span></span>   | <span data-ttu-id="c1aff-155">Envía `PRAGMA foreign_keys = 0` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="c1aff-156">(vacío)</span><span class="sxs-lookup"><span data-stu-id="c1aff-156">(empty)</span></span> | <span data-ttu-id="c1aff-157">No envía `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="c1aff-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="c1aff-158">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1aff-158">This is the default.</span></span> |

<span data-ttu-id="c1aff-159">No es necesario habilitar claves externas si, como en e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS se usó para compilar la biblioteca SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="c1aff-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="c1aff-160">Desencadenantes recursivos</span><span class="sxs-lookup"><span data-stu-id="c1aff-160">Recursive triggers</span></span>

<span data-ttu-id="c1aff-161">Valor que indica si se deben habilitar desencadenadores recursivos.</span><span class="sxs-lookup"><span data-stu-id="c1aff-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="c1aff-162">Value</span><span class="sxs-lookup"><span data-stu-id="c1aff-162">Value</span></span> | <span data-ttu-id="c1aff-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1aff-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="c1aff-164">True</span><span class="sxs-lookup"><span data-stu-id="c1aff-164">True</span></span>  | <span data-ttu-id="c1aff-165">Envía `PRAGMA recursive_triggers` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="c1aff-166">False</span><span class="sxs-lookup"><span data-stu-id="c1aff-166">False</span></span> | <span data-ttu-id="c1aff-167">No envía `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="c1aff-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="c1aff-168">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1aff-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="c1aff-169">Creador de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="c1aff-169">Connection string builder</span></span>

<span data-ttu-id="c1aff-170">Puede utilizarcomo <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> una forma fuertemente tipada de crear cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="c1aff-171">También se puede utilizar para evitar ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="c1aff-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="c1aff-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c1aff-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="c1aff-173">Básica</span><span class="sxs-lookup"><span data-stu-id="c1aff-173">Basic</span></span>

<span data-ttu-id="c1aff-174">Una cadena de conexión básica con una memoria caché compartida para mejorar la simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="c1aff-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="c1aff-175">Cifrados</span><span class="sxs-lookup"><span data-stu-id="c1aff-175">Encrypted</span></span>

<span data-ttu-id="c1aff-176">Una base de datos cifrada.</span><span class="sxs-lookup"><span data-stu-id="c1aff-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="c1aff-177">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c1aff-177">Read-only</span></span>

<span data-ttu-id="c1aff-178">Una base de datos de solo lectura que la aplicación no puede modificar.</span><span class="sxs-lookup"><span data-stu-id="c1aff-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="c1aff-179">En memoria</span><span class="sxs-lookup"><span data-stu-id="c1aff-179">In-memory</span></span>

<span data-ttu-id="c1aff-180">Una base de datos privada en memoria.</span><span class="sxs-lookup"><span data-stu-id="c1aff-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="c1aff-181">Apoderable en memoria</span><span class="sxs-lookup"><span data-stu-id="c1aff-181">Sharable in-memory</span></span>

<span data-ttu-id="c1aff-182">Una base de datos en memoria que se puede que se pueda hacer de forma personal identificada con el nombre *Sharable*.</span><span class="sxs-lookup"><span data-stu-id="c1aff-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="c1aff-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1aff-183">See also</span></span>

* [<span data-ttu-id="c1aff-184">Cadenas de conexión de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c1aff-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="c1aff-185">Bases de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="c1aff-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="c1aff-186">Transactions</span><span class="sxs-lookup"><span data-stu-id="c1aff-186">Transactions</span></span>](transactions.md)
