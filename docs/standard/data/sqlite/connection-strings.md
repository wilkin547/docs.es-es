---
title: Cadenas de conexión
ms.date: 12/13/2019
description: Las palabras clave y los valores admitidos de las cadenas de conexión.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401200"
---
# <a name="connection-strings"></a><span data-ttu-id="10c6f-103">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="10c6f-103">Connection strings</span></span>

<span data-ttu-id="10c6f-104">Una cadena de conexión que se usa para especificar cómo conectarse a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10c6f-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="10c6f-105">Las cadenas de conexión de Microsoft.Data.SQLite siguen la [sintaxis de ADO.NET](../../../framework/data/adonet/connection-strings.md) estándar como una lista de palabras clave y valores separados por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="10c6f-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="10c6f-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="10c6f-106">Keywords</span></span>

<span data-ttu-id="10c6f-107">Se pueden usar las palabras clave de cadena de conexión siguientes con Microsoft.Data.SQLite:</span><span class="sxs-lookup"><span data-stu-id="10c6f-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="10c6f-108">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="10c6f-108">Data source</span></span>

<span data-ttu-id="10c6f-109">Ruta de acceso al archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="10c6f-109">The path to the database file.</span></span> <span data-ttu-id="10c6f-110">*DataSource* (sin espacio) y *Filename* son alias de esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="10c6f-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="10c6f-111">SQLite trata las rutas de acceso relativas al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="10c6f-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="10c6f-112">También se pueden especificar rutas de acceso absolutas.</span><span class="sxs-lookup"><span data-stu-id="10c6f-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="10c6f-113">Si está **vacío**, SQLite crea una base de datos temporal en disco que se elimina al cerrar la conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="10c6f-114">Si es `:memory:`, se usa una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="10c6f-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="10c6f-115">Para más información, vea [Bases de datos en memoria](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="10c6f-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="10c6f-116">Las rutas de acceso que comienzan con la cadena de sustitución `|DataDirectory|` se tratan igual que las rutas de acceso relativas.</span><span class="sxs-lookup"><span data-stu-id="10c6f-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="10c6f-117">Si se establecen, las rutas de acceso son relativas al valor de propiedad de dominio de aplicación DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="10c6f-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="10c6f-118">Esta palabra clave también admite [nombres de archivo de URI](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="10c6f-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="10c6f-119">Modo</span><span class="sxs-lookup"><span data-stu-id="10c6f-119">Mode</span></span>

<span data-ttu-id="10c6f-120">Modo de conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-120">The connection mode.</span></span>

| <span data-ttu-id="10c6f-121">Valor</span><span class="sxs-lookup"><span data-stu-id="10c6f-121">Value</span></span>           | <span data-ttu-id="10c6f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c6f-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="10c6f-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="10c6f-123">ReadWriteCreate</span></span> | <span data-ttu-id="10c6f-124">Abre la base de datos para lectura y escritura, y la crea si no existe.</span><span class="sxs-lookup"><span data-stu-id="10c6f-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="10c6f-125">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10c6f-125">This is the default.</span></span> |
| <span data-ttu-id="10c6f-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="10c6f-126">ReadWrite</span></span>       | <span data-ttu-id="10c6f-127">Abre la base de datos para lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="10c6f-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="10c6f-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="10c6f-128">ReadOnly</span></span>        | <span data-ttu-id="10c6f-129">Abre la base de datos en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="10c6f-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="10c6f-130">Memoria</span><span class="sxs-lookup"><span data-stu-id="10c6f-130">Memory</span></span>          | <span data-ttu-id="10c6f-131">Abre una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="10c6f-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="10c6f-132">instancias y claves</span><span class="sxs-lookup"><span data-stu-id="10c6f-132">Cache</span></span>

<span data-ttu-id="10c6f-133">Modo de almacenamiento en caché que usa la conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="10c6f-134">Valor</span><span class="sxs-lookup"><span data-stu-id="10c6f-134">Value</span></span>   | <span data-ttu-id="10c6f-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c6f-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="10c6f-136">Default</span><span class="sxs-lookup"><span data-stu-id="10c6f-136">Default</span></span> | <span data-ttu-id="10c6f-137">Usa el modo predeterminado de la biblioteca de SQLite subyacente.</span><span class="sxs-lookup"><span data-stu-id="10c6f-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="10c6f-138">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10c6f-138">This is the default.</span></span>                   |
| <span data-ttu-id="10c6f-139">Private</span><span class="sxs-lookup"><span data-stu-id="10c6f-139">Private</span></span> | <span data-ttu-id="10c6f-140">Cada conexión usa una caché privada.</span><span class="sxs-lookup"><span data-stu-id="10c6f-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="10c6f-141">Shared</span><span class="sxs-lookup"><span data-stu-id="10c6f-141">Shared</span></span>  | <span data-ttu-id="10c6f-142">Las conexiones comparten una caché.</span><span class="sxs-lookup"><span data-stu-id="10c6f-142">Connections share a cache.</span></span> <span data-ttu-id="10c6f-143">Este modo puede cambiar el comportamiento del bloqueo de transacciones y tablas.</span><span class="sxs-lookup"><span data-stu-id="10c6f-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="10c6f-144">Contraseña</span><span class="sxs-lookup"><span data-stu-id="10c6f-144">Password</span></span>

<span data-ttu-id="10c6f-145">La clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="10c6f-145">The encryption key.</span></span> <span data-ttu-id="10c6f-146">Cuando se especifica, `PRAGMA key` se envía inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="10c6f-147">La contraseña no tiene ningún efecto cuando la biblioteca de SQLite nativa no admite el cifrado.</span><span class="sxs-lookup"><span data-stu-id="10c6f-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="10c6f-148">Claves externas</span><span class="sxs-lookup"><span data-stu-id="10c6f-148">Foreign Keys</span></span>

<span data-ttu-id="10c6f-149">Un valor que indica si se deben habilitar restricciones de clave externa.</span><span class="sxs-lookup"><span data-stu-id="10c6f-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="10c6f-150">Valor</span><span class="sxs-lookup"><span data-stu-id="10c6f-150">Value</span></span>   | <span data-ttu-id="10c6f-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c6f-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="10c6f-152">True</span><span class="sxs-lookup"><span data-stu-id="10c6f-152">True</span></span>    | <span data-ttu-id="10c6f-153">Se envía `PRAGMA foreign_keys = 1` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="10c6f-154">False</span><span class="sxs-lookup"><span data-stu-id="10c6f-154">False</span></span>   | <span data-ttu-id="10c6f-155">Se envía `PRAGMA foreign_keys = 0` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="10c6f-156">(vacío)</span><span class="sxs-lookup"><span data-stu-id="10c6f-156">(empty)</span></span> | <span data-ttu-id="10c6f-157">No se envía `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="10c6f-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="10c6f-158">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10c6f-158">This is the default.</span></span> |

<span data-ttu-id="10c6f-159">No es necesario habilitar las claves externas si, como en e_sqlite3, se ha usado SQLITE_DEFAULT_FOREIGN_KEYS para compilar la biblioteca nativa de SQLite.</span><span class="sxs-lookup"><span data-stu-id="10c6f-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="10c6f-160">Desencadenadores recursivos</span><span class="sxs-lookup"><span data-stu-id="10c6f-160">Recursive triggers</span></span>

<span data-ttu-id="10c6f-161">Un valor que indica si se van a habilitar los desencadenadores recursivos.</span><span class="sxs-lookup"><span data-stu-id="10c6f-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="10c6f-162">Valor</span><span class="sxs-lookup"><span data-stu-id="10c6f-162">Value</span></span> | <span data-ttu-id="10c6f-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c6f-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="10c6f-164">True</span><span class="sxs-lookup"><span data-stu-id="10c6f-164">True</span></span>  | <span data-ttu-id="10c6f-165">Se envía `PRAGMA recursive_triggers` inmediatamente después de abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="10c6f-166">False</span><span class="sxs-lookup"><span data-stu-id="10c6f-166">False</span></span> | <span data-ttu-id="10c6f-167">No se envía `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="10c6f-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="10c6f-168">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10c6f-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="10c6f-169">Generador de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="10c6f-169">Connection string builder</span></span>

<span data-ttu-id="10c6f-170">Puede usar <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> como una manera fuertemente tipada de crear cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="10c6f-171">También se pueda usar para evitar ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="10c6f-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="10c6f-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="10c6f-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="10c6f-173">Básico</span><span class="sxs-lookup"><span data-stu-id="10c6f-173">Basic</span></span>

<span data-ttu-id="10c6f-174">Una cadena de conexión básica con una memoria caché compartida para mejorar la simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="10c6f-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="10c6f-175">Cifrados</span><span class="sxs-lookup"><span data-stu-id="10c6f-175">Encrypted</span></span>

<span data-ttu-id="10c6f-176">Una base de datos cifrada.</span><span class="sxs-lookup"><span data-stu-id="10c6f-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="10c6f-177">De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="10c6f-177">Read-only</span></span>

<span data-ttu-id="10c6f-178">Una base de datos de solo lectura que la aplicación no puede modificar.</span><span class="sxs-lookup"><span data-stu-id="10c6f-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="10c6f-179">En memoria</span><span class="sxs-lookup"><span data-stu-id="10c6f-179">In-memory</span></span>

<span data-ttu-id="10c6f-180">Una base de datos en memoria privada.</span><span class="sxs-lookup"><span data-stu-id="10c6f-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="10c6f-181">En memoria que se pueda compartir</span><span class="sxs-lookup"><span data-stu-id="10c6f-181">Sharable in-memory</span></span>

<span data-ttu-id="10c6f-182">Una base de datos en memoria que se puede compartir y que se identifica mediante el nombre *Compartible*.</span><span class="sxs-lookup"><span data-stu-id="10c6f-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="10c6f-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="10c6f-183">See also</span></span>

* [<span data-ttu-id="10c6f-184">Cadenas de conexión de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="10c6f-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="10c6f-185">Bases de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="10c6f-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="10c6f-186">Transacciones</span><span class="sxs-lookup"><span data-stu-id="10c6f-186">Transactions</span></span>](transactions.md)
