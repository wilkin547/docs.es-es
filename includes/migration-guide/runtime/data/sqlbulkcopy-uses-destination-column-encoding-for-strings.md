---
ms.openlocfilehash: fd9f4f3de8f7be39242d4ff6924d480f20a1a06b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496611"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a><span data-ttu-id="62e0c-101">SqlBulkCopy usa la codificación de columna de destino para las cadenas</span><span class="sxs-lookup"><span data-stu-id="62e0c-101">SqlBulkCopy uses destination column encoding for strings</span></span>

#### <a name="details"></a><span data-ttu-id="62e0c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="62e0c-102">Details</span></span>

<span data-ttu-id="62e0c-103">Al insertar datos en una columna, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> utiliza la codificación de la columna de destino en lugar de la codificación predeterminada para los tipos <code>VARCHAR</code> y <code>CHAR</code>.</span><span class="sxs-lookup"><span data-stu-id="62e0c-103">When inserting data into a column, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> uses the encoding of the destination column rather than the default encoding for <code>VARCHAR</code> and <code>CHAR</code> types.</span></span> <span data-ttu-id="62e0c-104">Este cambio elimina la posibilidad de que se produzcan daños en los datos al usar la codificación predeterminada cuando la columna de destino no utiliza la codificación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="62e0c-104">This change eliminates the possibility of data corruption caused by using the default encoding when the destination column does not use the default encoding.</span></span> <span data-ttu-id="62e0c-105">En raras ocasiones, una aplicación existente podría iniciar una excepción SqlException si el cambio de codificación genera datos que son demasiado grandes como para caber en la columna de destino.</span><span class="sxs-lookup"><span data-stu-id="62e0c-105">In rare cases, an existing application may throw a SqlException exception if the change in encoding produces data that is too big to fit into the destination column.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="62e0c-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="62e0c-106">Suggestion</span></span>

<span data-ttu-id="62e0c-107">Espere que <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> ya no dañe los datos debido a diferencias de codificación.</span><span class="sxs-lookup"><span data-stu-id="62e0c-107">Expect that <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> will no longer corrupt data due to encoding differences.</span></span> <span data-ttu-id="62e0c-108">Si se copian cadenas cerca del límite de tamaño de la columna de destino, puede que sea necesario codificar previamente los datos (que se van a copiar para comprobar que caben en la columna de destino) o capturar las excepciones <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="62e0c-108">If strings near the destination column's size limit are being copied, it may be necessary to either pre-encode data (to be copied to check that the data will fit in the destination column) or catch <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="62e0c-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="62e0c-109">Name</span></span>    | <span data-ttu-id="62e0c-110">Valor</span><span class="sxs-lookup"><span data-stu-id="62e0c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="62e0c-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="62e0c-111">Scope</span></span>   |<span data-ttu-id="62e0c-112">Borde</span><span class="sxs-lookup"><span data-stu-id="62e0c-112">Edge</span></span>|
|<span data-ttu-id="62e0c-113">Versión</span><span class="sxs-lookup"><span data-stu-id="62e0c-113">Version</span></span>|<span data-ttu-id="62e0c-114">4.5</span><span class="sxs-lookup"><span data-stu-id="62e0c-114">4.5</span></span>|
|<span data-ttu-id="62e0c-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="62e0c-115">Type</span></span>|<span data-ttu-id="62e0c-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="62e0c-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="62e0c-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="62e0c-117">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)>

<!--

#### Affected APIs

- `T:System.Data.SqlClient.SqlBulkCopy`
- `M:System.Data.SqlClient.SqlBulkCopy.#ctor(System.Data.SqlClient.SqlConnection)`

-->
