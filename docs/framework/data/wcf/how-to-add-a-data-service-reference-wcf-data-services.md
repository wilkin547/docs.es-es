---
title: Procedimiento Agregar una referencia de servicio de datos (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 8bf623ec74c3bd165f63f60e883bfcb532d6900b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633952"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Procedimiento Agregar una referencia de servicio de datos (WCF Data Services)

Puede usar el **Add Service Reference** cuadro de diálogo de Visual Studio para agregar una referencia a WCF Data Services. Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio. Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos. Para obtener más información, consulte [generar la biblioteca de cliente de servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).

## <a name="add-a-data-service-reference"></a>Agregar una referencia de servicio de datos

1. (Opcional) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.

2. En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto de cliente y, a continuación, seleccione **agregar** > **referencia de servicio**.

3. Si el servicio de datos forma parte de la solución actual, haga clic en **Discover**.

     -o bien-

     En el **dirección** cuadro de texto, escriba la dirección URL base del servicio de datos, como `http://localhost:1234/Northwind.svc`y, a continuación, haga clic en **vaya**.

4. Seleccione **Aceptar**.

     Un nuevo archivo de código que contiene las clases de datos que pueden obtener acceso e interactuar con los recursos de servicio de datos se agrega al proyecto.

## <a name="see-also"></a>Vea también

- [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
