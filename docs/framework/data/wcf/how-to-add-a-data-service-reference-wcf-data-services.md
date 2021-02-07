---
description: 'Más información acerca de cómo: agregar una referencia de servicio de datos (Servicios de datos de WCF)'
title: 'Cómo: Agregar una referencia a Data Services (Data Services de WCF)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 907ad9a7dc3710a6e565de55c74a0d279d20e159
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765761"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Cómo: agregar una referencia de servicio de datos (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a servicios de datos de WCF. Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio. Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos. Para obtener más información, vea [generar la biblioteca de cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md).

## <a name="add-a-data-service-reference"></a>Agregar una referencia de servicio de datos

1. (Opcional) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.

2. En el **Explorador de soluciones** de Visual Studio, haga clic con el botón secundario en el proyecto de cliente y, a continuación, seleccione **Agregar**  >  **referencia de servicio**.

3. Si el servicio de datos forma parte de la solución actual, haga clic en **detectar**.

     o bien

     En el cuadro de texto **Dirección** , escriba la dirección URL base del servicio de datos, como `http://localhost:1234/Northwind.svc` y, a continuación, haga clic en **ir**.

4. Seleccione **Aceptar**.

     Se agrega al proyecto un nuevo archivo de código que contiene las clases de datos que pueden tener acceso e interactuar con los recursos del servicio de datos.

## <a name="see-also"></a>Vea también

- [Guía de inicio rápido](quickstart-wcf-data-services.md)
