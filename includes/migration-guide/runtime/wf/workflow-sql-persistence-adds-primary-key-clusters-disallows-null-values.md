---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621394"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="3d9f4-101">La persistencia SQL de flujo de trabajo agrega clústeres de clave principal y no permite valores NULL en algunas columnas</span><span class="sxs-lookup"><span data-stu-id="3d9f4-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="3d9f4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3d9f4-102">Details</span></span>

<span data-ttu-id="3d9f4-103">A partir de .NET Framework 4.7, en las tablas creadas para el almacén de instancias de flujo de trabajo de SQL (SWIS) por el script SqlWorkflowInstanceStoreSchema.sql se usan claves principales en clúster.</span><span class="sxs-lookup"><span data-stu-id="3d9f4-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="3d9f4-104">Por este motivo, las identidades no admiten valores <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="3d9f4-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="3d9f4-105">El funcionamiento de SWIS no se ve afectado por este cambio.</span><span class="sxs-lookup"><span data-stu-id="3d9f4-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="3d9f4-106">Las actualizaciones se realizaron para admitir la replicación transaccional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d9f4-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3d9f4-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3d9f4-107">Suggestion</span></span>

<span data-ttu-id="3d9f4-108">El archivo SQL SqlWorkflowInstanceStoreSchemaUpgrade.sql se debe aplicar a las instalaciones existentes con el fin de experimentar este cambio.</span><span class="sxs-lookup"><span data-stu-id="3d9f4-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="3d9f4-109">Las nuevas instalaciones de base de datos tendrán automáticamente el cambio.</span><span class="sxs-lookup"><span data-stu-id="3d9f4-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="3d9f4-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="3d9f4-110">Name</span></span>    | <span data-ttu-id="3d9f4-111">Valor</span><span class="sxs-lookup"><span data-stu-id="3d9f4-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3d9f4-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3d9f4-112">Scope</span></span>   |<span data-ttu-id="3d9f4-113">Borde</span><span class="sxs-lookup"><span data-stu-id="3d9f4-113">Edge</span></span>|
|<span data-ttu-id="3d9f4-114">Versión</span><span class="sxs-lookup"><span data-stu-id="3d9f4-114">Version</span></span>|<span data-ttu-id="3d9f4-115">4.7</span><span class="sxs-lookup"><span data-stu-id="3d9f4-115">4.7</span></span>|
|<span data-ttu-id="3d9f4-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d9f4-116">Type</span></span>|<span data-ttu-id="3d9f4-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3d9f4-117">Runtime</span></span>|
