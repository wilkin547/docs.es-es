---
title: 'Personalizar operaciones: Información general'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 29fb75271b7bc324d462078e94e4a28534986fba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038096"
---
# <a name="customizing-operations-overview"></a>Personalizar operaciones: Información general
De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera SQL dinámico para las operaciones de inserción, actualización y eliminación por asignación. Sin embargo, en la práctica, normalmente se agrega lógica empresarial propia para proporcionar seguridad, validación, etc.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las técnicas para personalizar estas operaciones incluyen lo siguiente.  
  
## <a name="loading-options"></a>Opciones de carga  
 En las consultas es posible controlar la cantidad de datos relacionados con el destino principal que se recuperan al establecer una conexión con la base de datos. Esta funcionalidad se implementa en gran medida mediante el uso de <xref:System.Data.Linq.DataLoadOptions>. Para obtener más información, consulte [carga inmediata y carga diferida](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Métodos Partial  
 En su asignación predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona métodos parciales para ayudar a implementar lógica empresarial propia. Para obtener más información, consulte [agregar Business Logic por utilizando métodos parciales](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Procedimientos almacenados y funciones definidas por el usuario  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite el uso de procedimientos almacenados y funciones definidas por el usuario. Los procedimientos almacenados se utilizan con frecuencia para personalizar operaciones. Para obtener más información, vea [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Vea también

- [Personalización de operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
