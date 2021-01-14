---
title: Información general de Azure SDK para .NET
description: En este artículo se proporciona información general sobre qué es Azure SDK para .NET y sobre los pasos básicos para usar el SDK en una aplicación de .NET.
ms.date: 11/30/2020
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 3ec1ee9e8da3a6e03581ce2a29a655ec0d68fe54
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701014"
---
# <a name="azure-sdk-for-net-overview"></a>Información general de Azure SDK para .NET

## <a name="what-is-the-azure-sdk-for-net"></a>¿Qué es Azure SDK para .NET?

**Azure SDK para .NET** está diseñado para facilitar el uso de los servicios de Azure desde las aplicaciones de .NET.  Azure SDK para .NET proporciona una interfaz coherente y familiar para acceder a los servicios de Azure, ya sea para cargar o descargar archivos en Blob Storage, recuperar los secretos de la aplicación en Azure Key Vault o procesar notificaciones de Azure Event Hubs.  

Azure SDK para .NET está disponible como una serie de paquetes NuGet que se pueden usar en aplicaciones de .NET Core (2.1 y versiones posteriores) y .NET Framework (4.6.1 y versiones posteriores).

![Diagrama en el que se muestra cómo usan las aplicaciones .NET el SDK de Azure para acceder a los servicios de Azure](./media/azure-sdk-for-dotnet-overview.png)

## <a name="use-the-azure-sdk-for-net-in-your-applications"></a>Uso de Azure SDK para .NET en las aplicaciones

Para usar un paquete del SDK de Azure en una de sus aplicaciones de .NET, siga estos pasos:

1. **Localización del paquete del SDK adecuado**: use la [lista de paquetes](../packages.md) para encontrar el paquete adecuado para el servicio de Azure con el que está trabajando.  Tenga en cuenta que la mayoría de los servicios tienen un paquete de cliente para trabajar con el servicio y un paquete de administración para crear y administrar instancias de dicho servicio.  En la mayoría de los casos, le interesará el paquete de cliente.  Instale este paquete en la aplicación mediante NuGet.

2. **Configuración de la autenticación para la aplicación**: para poder acceder a los recursos de Azure, la aplicación necesitará tener las credenciales y los derechos de acceso adecuados asignados en Azure.  Para aprender a configurar la autenticación, consulte el artículo [Autenticación con SDK de Azure para .NET](../authentication.md).

3. **Escritura de código mediante el SDK en la aplicación**: al trabajar con un servicio de Azure, su código creará primero un objeto de cliente para trabajar con el servicio y, después, llamará a métodos en ese objeto de cliente para interactuar con el servicio.  Se proporcionan métodos sincrónicos y asincrónicos.  En la documentación de Azure se proporcionan ejemplos de uso de cada uno de los paquetes del SDK.

4. **Configuración del registro para el SDK (opcional)** : si necesita diagnosticar problemas entre la aplicación y Azure, puede [habilitar el registro con Azure SDK para .NET](./logging.md).
