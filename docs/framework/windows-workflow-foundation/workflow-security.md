---
title: Seguridad del flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
ms.openlocfilehash: 36d03a2fca8f143b98338050fc9da4490960bda9
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837524"
---
# <a name="workflow-security"></a>Seguridad del flujo de trabajo
Windows Workflow Foundation (WF) se integra con varias tecnologías diferentes, como Microsoft SQL Server y Windows Communication Foundation (WCF). Al interactuar con estas tecnologías, se pueden introducir problemas de seguridad en su flujo de trabajo si no se hace de manera correcta.

## <a name="persistence-security-concerns"></a>Problemas de seguridad de persistencia

1. Los flujos de trabajo que usan una actividad <xref:System.Activities.Statements.Delay> y persistencia se deben reactivar mediante un servicio. Windows AppFabric usa el Servicio de administración de flujos de trabajo (WMS) para reactivar flujos de trabajo con temporizadores expirados. WMS crea un <xref:System.ServiceModel.WorkflowServiceHost> para hospedar el flujo de trabajo reactivado. Si se detiene el servicio de WMS, los flujos de trabajo conservados no se reactivarán cuando sus temporizadores expiren.

2. El acceso a la creación de instancias duraderas debe protegerse contra entidades malintencionadas externas al dominio de aplicación. Además, los desarrolladores deben asegurarse de que el código malintencionado no se pueda ejecutar en el mismo dominio de aplicación que el código de creación de instancias duraderas.

3. La creación de instancias duraderas no se debe ejecutar con permisos elevados (administrador).

4. Los datos que se procesan fuera del dominio de aplicación deben ser protegidos.

5. Las aplicaciones que necesitan aislamiento de seguridad no deben compartir la misma instancia de abstracción de esquema. Dichas aplicaciones deben usar proveedores de almacén diferentes o proveedores de almacén configurados usar diferentes instancias de almacén.

## <a name="sql-server-security-concerns"></a>Problemas de seguridad de SQL Server

- Cuando se usan numerosas actividades secundarias, ubicaciones, marcadores, extensiones de host o ámbitos, o cuando se usan marcadores con grandes cantidades de carga, puede ocurrir que la memoria se acabe o que se asignen cantidades indebidas de espacio a la base de datos durante la persistencia. Este hecho se puede reducir usando la seguridad del nivel de objeto o de la base de datos.

- Al usar <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, se debe proteger el almacén de instancias.

- Se deberían cifrar los datos confidenciales del almacén de instancias. Para más información, consulte [SQL Server Encryption](/sql/relational-databases/security/encryption/sql-server-encryption).

- Puesto que la cadena de conexión a bases de datos se suele incluir en un archivo de configuración, la seguridad de nivel de Windows (ACL) se debe usar para asegurarse de que el archivo de configuración (Web.Config normalmente) es seguro, y que la información de inicio de sesión y contraseña no se incluyen en la cadena de conexión. La autenticación de Windows se debe usar entre la base de datos y el servidor web en su lugar.

## <a name="considerations-for-workflowservicehost"></a>Consideraciones para WorkflowServiceHost

- Se deben proteger los puntos de conexión de Windows Communication Foundation (WCF) utilizados en flujos de trabajo. Para obtener más información, vea [información general sobre la seguridad de WCF](../wcf/feature-details/security-overview.md).

- La autorización en el nivel de host puede implementarse mediante <xref:System.ServiceModel.ServiceAuthorizationManager>. Consulte [Cómo: crear un administrador de autorización personalizado para un servicio](../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md) para obtener más información.

- El ServiceSecurityContext para el mensaje entrante también está disponible desde el flujo de trabajo mediante el acceso a OperationContext.

## <a name="wf-security-pack-ctp"></a>CTP del paquete de seguridad de WF
 El paquete de seguridad de Microsoft WF CTP 1 es la primera versión Community Technology Preview (CTP) de un conjunto de actividades y su implementación basada en [Windows Workflow Foundation](index.md) en [.NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w0x726c2(v=vs.100)) (WF 4) y [Windows Identity Foundation (WIF)](../security/index.md).  El CTP 1 del paquete de seguridad de Microsoft WF contiene ambas actividades y sus diseñadores que muestran cómo habilitar fácilmente diferentes escenarios relacionados con la seguridad usando el flujo de trabajo, incluidas:

1. Suplantar una identidad del cliente en el flujo de trabajo

2. Autorización en el flujo de trabajo, como PrincipalPermission y validación de notificaciones

3. Mensajería autenticada mediante ClientCredentials especificadas en el flujo de trabajo, como nombre de usuario/contraseña o un token recuperado de un Servicio de token de seguridad (STS)

4. Llevar un token de seguridad de cliente a un servicio de fondo (delegación basada en notificaciones) mediante ActAs de WS-Trust

Para obtener más información y descargar el CTP del paquete de seguridad de WF, vea: [WF Security Pack CTP](https://archive.codeplex.com/?p=wf)
