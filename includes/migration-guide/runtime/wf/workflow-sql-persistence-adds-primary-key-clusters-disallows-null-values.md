---
ms.openlocfilehash: 9e98d3bca645cf82bf4fe99160dd096b0e274ef7
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760444"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="bf0b4-101">La persistencia SQL de flujo de trabajo agrega clústeres de clave principal y no permite valores NULL en algunas columnas</span><span class="sxs-lookup"><span data-stu-id="bf0b4-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bf0b4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="bf0b4-102">Details</span></span>|<span data-ttu-id="bf0b4-103">A partir de .NET Framework 4.7, en las tablas creadas para el almacén de instancias de flujo de trabajo de SQL (SWIS) por el script SqlWorkflowInstanceStoreSchema.sql se usan claves principales en clúster.</span><span class="sxs-lookup"><span data-stu-id="bf0b4-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="bf0b4-104">Por este motivo, las identidades no admiten valores <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="bf0b4-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="bf0b4-105">El funcionamiento de SWIS no se ve afectado por este cambio.</span><span class="sxs-lookup"><span data-stu-id="bf0b4-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="bf0b4-106">Las actualizaciones se realizaron para admitir la replicación transaccional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf0b4-106">The updates were made to support SQL Server Transactional Replication.</span></span>|
|<span data-ttu-id="bf0b4-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="bf0b4-107">Suggestion</span></span>|<span data-ttu-id="bf0b4-108">El archivo SQL SqlWorkflowInstanceStoreSchemaUpgrade.sql se debe aplicar a las instalaciones existentes con el fin de experimentar este cambio.</span><span class="sxs-lookup"><span data-stu-id="bf0b4-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="bf0b4-109">Las nuevas instalaciones de base de datos tendrán automáticamente el cambio.</span><span class="sxs-lookup"><span data-stu-id="bf0b4-109">New database installations will automatically have the change.</span></span>|
|<span data-ttu-id="bf0b4-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bf0b4-110">Scope</span></span>|<span data-ttu-id="bf0b4-111">Borde</span><span class="sxs-lookup"><span data-stu-id="bf0b4-111">Edge</span></span>|
|<span data-ttu-id="bf0b4-112">Versión</span><span class="sxs-lookup"><span data-stu-id="bf0b4-112">Version</span></span>|<span data-ttu-id="bf0b4-113">4.7</span><span class="sxs-lookup"><span data-stu-id="bf0b4-113">4.7</span></span>|
|<span data-ttu-id="bf0b4-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="bf0b4-114">Type</span></span>|<span data-ttu-id="bf0b4-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bf0b4-115">Runtime</span></span>|

