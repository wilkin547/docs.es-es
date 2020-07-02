---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621394"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>La persistencia SQL de flujo de trabajo agrega clústeres de clave principal y no permite valores NULL en algunas columnas

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7, en las tablas creadas para el almacén de instancias de flujo de trabajo de SQL (SWIS) por el script SqlWorkflowInstanceStoreSchema.sql se usan claves principales en clúster. Por este motivo, las identidades no admiten valores <code>null</code>. El funcionamiento de SWIS no se ve afectado por este cambio. Las actualizaciones se realizaron para admitir la replicación transaccional de SQL Server.

#### <a name="suggestion"></a>Sugerencia

El archivo SQL SqlWorkflowInstanceStoreSchemaUpgrade.sql se debe aplicar a las instalaciones existentes con el fin de experimentar este cambio. Las nuevas instalaciones de base de datos tendrán automáticamente el cambio.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7|
|Tipo|Tiempo de ejecución|
