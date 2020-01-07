---
title: Cadenas de conexión
ms.date: 12/13/2019
description: Las palabras clave y los valores admitidos de las cadenas de conexión.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450277"
---
# <a name="connection-strings"></a><span data-ttu-id="341ab-103">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="341ab-103">Connection strings</span></span>

<span data-ttu-id="341ab-104">Se utiliza una cadena de conexión para especificar cómo conectarse a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="341ab-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="341ab-105">Las cadenas de conexión de Microsoft. Data. SQLite siguen la sintaxis estándar de [ADO.net](../../../framework/data/adonet/connection-strings.md) como una lista de palabras clave y valores separadas por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="341ab-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="341ab-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="341ab-106">Keywords</span></span>

<span data-ttu-id="341ab-107">Se pueden usar las siguientes palabras clave de cadena de conexión con Microsoft. Data. SQLite:</span><span class="sxs-lookup"><span data-stu-id="341ab-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="341ab-108">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="341ab-108">Data source</span></span>

<span data-ttu-id="341ab-109">Ruta de acceso al archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="341ab-109">The path to the database file.</span></span> <span data-ttu-id="341ab-110">*DataSource* (sin espacio) y *filename* son alias de esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="341ab-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="341ab-111">SQLite trata las rutas de acceso relativas al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="341ab-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="341ab-112">También se pueden especificar rutas de acceso absolutas.</span><span class="sxs-lookup"><span data-stu-id="341ab-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="341ab-113">Si **está vacío**, SQLite crea una base de datos temporal en disco que se elimina cuando se cierra la conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="341ab-114">Si `:memory:`, se utiliza una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="341ab-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="341ab-115">Para obtener más información, vea [bases de datos en memoria](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="341ab-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="341ab-116">Las rutas de acceso que comienzan con la cadena de sustitución `|DataDirectory|` se tratan igual que las rutas de acceso relativas.</span><span class="sxs-lookup"><span data-stu-id="341ab-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="341ab-117">Si se establece, las rutas de acceso se realizan en relación con el valor de propiedad de dominio de aplicación DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="341ab-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="341ab-118">Esta palabra clave también admite [nombres de archivo de URI](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="341ab-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="341ab-119">Modo</span><span class="sxs-lookup"><span data-stu-id="341ab-119">Mode</span></span>

<span data-ttu-id="341ab-120">El modo de conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-120">The connection mode.</span></span>

| <span data-ttu-id="341ab-121">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="341ab-121">Value</span></span>           | <span data-ttu-id="341ab-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="341ab-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="341ab-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="341ab-123">ReadWriteCreate</span></span> | <span data-ttu-id="341ab-124">Abre la base de datos para lectura y escritura, y la crea si no existe.</span><span class="sxs-lookup"><span data-stu-id="341ab-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="341ab-125">Esta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="341ab-125">This is the default.</span></span> |
| <span data-ttu-id="341ab-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="341ab-126">ReadWrite</span></span>       | <span data-ttu-id="341ab-127">Abre la base de datos para lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="341ab-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="341ab-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="341ab-128">ReadOnly</span></span>        | <span data-ttu-id="341ab-129">Abre la base de datos en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="341ab-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="341ab-130">Memoria</span><span class="sxs-lookup"><span data-stu-id="341ab-130">Memory</span></span>          | <span data-ttu-id="341ab-131">Abre una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="341ab-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="341ab-132">instancias y claves</span><span class="sxs-lookup"><span data-stu-id="341ab-132">Cache</span></span>

<span data-ttu-id="341ab-133">Modo de almacenamiento en caché utilizado por la conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="341ab-134">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="341ab-134">Value</span></span>   | <span data-ttu-id="341ab-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="341ab-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="341ab-136">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="341ab-136">Default</span></span> | <span data-ttu-id="341ab-137">Usa el modo predeterminado de la biblioteca de SQLite subyacente.</span><span class="sxs-lookup"><span data-stu-id="341ab-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="341ab-138">Esta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="341ab-138">This is the default.</span></span>                   |
| <span data-ttu-id="341ab-139">Private</span><span class="sxs-lookup"><span data-stu-id="341ab-139">Private</span></span> | <span data-ttu-id="341ab-140">Cada conexión utiliza una caché privada.</span><span class="sxs-lookup"><span data-stu-id="341ab-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="341ab-141">Compartido</span><span class="sxs-lookup"><span data-stu-id="341ab-141">Shared</span></span>  | <span data-ttu-id="341ab-142">Las conexiones comparten una caché.</span><span class="sxs-lookup"><span data-stu-id="341ab-142">Connections share a cache.</span></span> <span data-ttu-id="341ab-143">Este modo puede cambiar el comportamiento del bloqueo de transacciones y tablas.</span><span class="sxs-lookup"><span data-stu-id="341ab-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="341ab-144">Password</span><span class="sxs-lookup"><span data-stu-id="341ab-144">Password</span></span>

<span data-ttu-id="341ab-145">La clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="341ab-145">The encryption key.</span></span> <span data-ttu-id="341ab-146">Cuando se especifica, `PRAGMA key` se envía inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="341ab-147">La contraseña no tiene ningún efecto cuando la biblioteca de SQLite nativa no admite el cifrado.</span><span class="sxs-lookup"><span data-stu-id="341ab-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="341ab-148">Claves externas</span><span class="sxs-lookup"><span data-stu-id="341ab-148">Foreign Keys</span></span>

<span data-ttu-id="341ab-149">Valor que indica si se van a habilitar las restricciones Foreign Key.</span><span class="sxs-lookup"><span data-stu-id="341ab-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="341ab-150">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="341ab-150">Value</span></span>   | <span data-ttu-id="341ab-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="341ab-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="341ab-152">Verdadero</span><span class="sxs-lookup"><span data-stu-id="341ab-152">True</span></span>    | <span data-ttu-id="341ab-153">Envía `PRAGMA foreign_keys = 1` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="341ab-154">Falso</span><span class="sxs-lookup"><span data-stu-id="341ab-154">False</span></span>   | <span data-ttu-id="341ab-155">Envía `PRAGMA foreign_keys = 0` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="341ab-156">(vacío)</span><span class="sxs-lookup"><span data-stu-id="341ab-156">(empty)</span></span> | <span data-ttu-id="341ab-157">No envía `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="341ab-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="341ab-158">Esta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="341ab-158">This is the default.</span></span> |

<span data-ttu-id="341ab-159">No es necesario habilitar las claves externas si, como en e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS se usó para compilar la biblioteca nativa de SQLite.</span><span class="sxs-lookup"><span data-stu-id="341ab-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="341ab-160">Desencadenadores recursivos</span><span class="sxs-lookup"><span data-stu-id="341ab-160">Recursive triggers</span></span>

<span data-ttu-id="341ab-161">Valor que indica si se van a habilitar los desencadenadores recursivos.</span><span class="sxs-lookup"><span data-stu-id="341ab-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="341ab-162">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="341ab-162">Value</span></span> | <span data-ttu-id="341ab-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="341ab-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="341ab-164">Verdadero</span><span class="sxs-lookup"><span data-stu-id="341ab-164">True</span></span>  | <span data-ttu-id="341ab-165">Envía `PRAGMA recursive_triggers` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="341ab-166">Falso</span><span class="sxs-lookup"><span data-stu-id="341ab-166">False</span></span> | <span data-ttu-id="341ab-167">No envía `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="341ab-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="341ab-168">Esta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="341ab-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="341ab-169">Generador de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="341ab-169">Connection string builder</span></span>

<span data-ttu-id="341ab-170">Puede usar <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> como una manera fuertemente tipada de crear cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="341ab-171">También se puede utilizar para evitar ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="341ab-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="341ab-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="341ab-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="341ab-173">Basic</span><span class="sxs-lookup"><span data-stu-id="341ab-173">Basic</span></span>

<span data-ttu-id="341ab-174">Una cadena de conexión básica con una memoria caché compartida para mejorar la simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="341ab-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="341ab-175">Cifrado</span><span class="sxs-lookup"><span data-stu-id="341ab-175">Encrypted</span></span>

<span data-ttu-id="341ab-176">Una base de datos cifrada.</span><span class="sxs-lookup"><span data-stu-id="341ab-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="341ab-177">De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="341ab-177">Read-only</span></span>

<span data-ttu-id="341ab-178">Una base de datos de solo lectura que la aplicación no puede modificar.</span><span class="sxs-lookup"><span data-stu-id="341ab-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="341ab-179">En memoria</span><span class="sxs-lookup"><span data-stu-id="341ab-179">In-memory</span></span>

<span data-ttu-id="341ab-180">Una base de datos privada en memoria.</span><span class="sxs-lookup"><span data-stu-id="341ab-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="341ab-181">En memoria que se pueda compartir</span><span class="sxs-lookup"><span data-stu-id="341ab-181">Sharable in-memory</span></span>

<span data-ttu-id="341ab-182">Una base de datos en memoria que se pueda compartir y que se identifica mediante el nombre que se pueda *compartir*.</span><span class="sxs-lookup"><span data-stu-id="341ab-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="341ab-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="341ab-183">See also</span></span>

* [<span data-ttu-id="341ab-184">Cadenas de conexión en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="341ab-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="341ab-185">Bases de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="341ab-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="341ab-186">Transacciones</span><span class="sxs-lookup"><span data-stu-id="341ab-186">Transactions</span></span>](transactions.md)
