---
title: El bloque de creación de secretos de DAPR
description: Una descripción del bloque de creación de secretos, sus características, ventajas y cómo aplicarlo
author: edwinvw
ms.date: 02/17/2021
ms.openlocfilehash: 52b899b4d496aab6762f69bbee99faecfcd23d59
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623751"
---
# <a name="the-dapr-secrets-building-block"></a>El bloque de creación de secretos de DAPR

Las aplicaciones empresariales requieren secretos. Algunos ejemplos frecuentes son:

- Una cadena de conexión de base de datos que contiene un nombre de usuario y una contraseña.
- Una clave de API para llamar a una API web externa.
- Un certificado de cliente para autenticarse en un sistema externo.

Los secretos deben administrarse con cuidado para que nunca se revelen fuera de la aplicación.

No hace mucho tiempo, era popular almacenar los secretos de aplicación en un archivo de configuración dentro del código base de la aplicación. Los desarrolladores de .NET recordarán el archivo de *web.config* . Aunque es fácil de implementar, la integración de secretos en junto con el código era muy segura. Un error frecuente era incluir el archivo al insertarlo en un repositorio de GIT público y exponer los secretos al mundo.

Una metodología ampliamente aceptada para construir aplicaciones distribuidas modernas es [la aplicación Twelve-Factor](https://12factor.net/). Describe un conjunto de principios y prácticas recomendadas. Su tercer factor prescribe que *la configuración y los secretos se externalizan fuera de la base de código.*

Para solucionar este problema, la plataforma .NET Core incluye una característica de [Administrador secreto](/aspnet/core/security/app-secrets#secret-manager) que almacena datos confidenciales en una carpeta física fuera del árbol del proyecto. Aunque los secretos están fuera del control de código fuente, esta característica no cifra los datos. Está diseñado solo para **fines de desarrollo** .

Una práctica más moderna y segura consiste en aislar secretos en una herramienta de administración de secretos como **Hashicorp Vault** o **Azure Key Vault**.  Estas herramientas permiten almacenar secretos externamente, variar las credenciales entre entornos y hacer referencia a ellos desde el código de la aplicación. Sin embargo, cada herramienta tiene sus complejidades y la curva de aprendizaje.

DAPR ofrece un bloque de creación que simplifica la administración de secretos.

## <a name="what-it-solves"></a>Qué resuelve

El [bloque de creación de secretos](https://docs.dapr.io/developing-applications/building-blocks/secrets/secrets-overview/) de DAPR abstrae la complejidad del trabajo con secretos y herramientas de administración de secretos.

- Oculta la fontanería subyacente a través de una interfaz unificada.
- Admite varios componentes del almacén de secretos *conectables* , que pueden variar entre el desarrollo y la producción.
- Las aplicaciones no requieren dependencias directas en las bibliotecas de almacenamiento de secretos.
- Los desarrolladores no requieren un conocimiento detallado de cada almacén de secretos.

DAPR controla todos los problemas anteriores.

El acceso a los secretos se protege a través de la autenticación y la autorización. Solo una aplicación con derechos suficientes puede acceder a los secretos. Las aplicaciones que se ejecutan en Kubernetes también pueden usar su mecanismo de administración de secretos integrado.

## <a name="how-it-works"></a>Cómo funciona

Las aplicaciones usan el bloque de creación de secretos de dos maneras:

- Recupere un secreto directamente desde el bloque de aplicación.
- Hacer referencia a un secreto indirectamente desde una configuración de componente de DAPR.

Primero se trata la recuperación de secretos directamente. La referencia a un secreto desde un archivo de configuración de componentes de DAPR se trata en una sección posterior.

La aplicación interactúa con un sidecar de DAPR cuando se usa el bloque de creación de secretos. El sidecar expone la API de secretos. Se puede llamar a la API con HTTP o gRPC. Use la siguiente dirección URL para llamar a la API HTTP:

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/<name>?<metadata>
```

La dirección URL contiene los segmentos siguientes:

- `<dapr-port>` especifica el número de puerto en el que escucha el sidecar de DAPR.
- `<store-name>` especifica el nombre del almacén de secretos de DAPR.
- `<name>` especifica el nombre del secreto que se va a recuperar.
- `<metadata>` proporciona información adicional para el secreto. Este segmento es opcional y las propiedades de metadatos difieren en cada almacén secreto. Para obtener más información sobre las propiedades de metadatos, consulte la referencia de la [API de secretos]([Secrets API reference | Dapr Docs](https://docs.dapr.io/reference/api/secrets_api/)).

 > [!NOTE]
 > La dirección URL anterior representa la llamada de API de DAPR nativa disponible para cualquier plataforma de desarrollo que admita HTTP o gRPC. Las plataformas populares como .NET, Java y go tienen sus propias API personalizadas.

La respuesta JSON contiene la clave y el valor del secreto.

En la figura 10-1 se muestra cómo DAPR controla una solicitud de la API de secretos:

![Diagrama de recuperación de un secreto mediante la API de secretos de DAPR.](media/secrets/secrets-flow.png)

**Figura 10-1**. Recuperación de un secreto con la API de secretos de DAPR.

1. El servicio llama a la API DAPR Secrets, junto con el nombre del almacén secreto y el secreto que se va a recuperar.
1. El sidecar de DAPR recupera el secreto especificado del almacén de secretos.
1. El sidecar DAPR devuelve la información secreta al servicio.

Algunos almacenes secretos admiten el almacenamiento de varios pares clave-valor en un único secreto. En estos casos, la respuesta contendría varios pares clave-valor en una única respuesta JSON como en el ejemplo siguiente:

```http
GET http://localhost:3500/v1.0/secrets/secret-store/interestRates?metadata.version_id=3
```

```json
{
  "tier1-percentage": "2.5",
  "tier2-percentage": "3.8",
  "tier3-percentage": "5.1"
}
```

La API DAPR Secrets también ofrece una operación para recuperar todos los secretos a los que la aplicación tiene acceso:

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/bulk
```

## <a name="use-the-dapr-net-sdk"></a>Uso del SDK de .NET para DAPR

Para los desarrolladores de .NET, el SDK de .NET para DAPR simplifica la administración de secretos de DAPR. Considere el `DaprClient.GetSecretAsync` método. Permite recuperar un secreto directamente de cualquier almacén de secretos de DAPR con un esfuerzo mínimo. A continuación se muestra un ejemplo de obtención de un secreto de cadena de conexión para una base de datos SQL Server:

```csharp
var metadata = new Dictionary<string, string> { ["version_id"] = "3" };
Dictionary<string, string> secrets = await daprClient.GetSecretAsync("secret-store", "eshopsecrets", metadata);
string connectionString = secrets["customerdb"];
```

Los argumentos del `GetSecretAsync` método incluyen:

- Nombre del componente de almacén de secretos de DAPR (' almacén de secretos ')
- Secreto que se va a recuperar (' eshopsecrets ')
- Pares de clave/valor de metadatos opcionales (' version_id = 3 ')

El método responde con un objeto de diccionario como secreto puede contener varios pares clave-valor. En el ejemplo anterior, `customerdb` se hace referencia al secreto denominado desde la colección para devolver una cadena de conexión.

El SDK de .NET de DAPR también incluye un proveedor de configuración de .NET. Carga los secretos especificados en la [API de configuración subyacente de .net Core](../../core/extensions/configuration.md). La aplicación en ejecución puede hacer referencia a los secretos del `IConfiguration` Diccionario registrado en ASP.net Core la inserción de dependencias.

El proveedor de configuración de secretos está disponible en el paquete NuGet [Dapr.Extensions.Configprimario](https://www.nuget.org/packages/Dapr.Extensions.Configuration) . El proveedor se puede registrar en la `Program.cs` de una aplicación ASP.net web API:  

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureAppConfiguration(config =>
        {
            var daprClient = new DaprClientBuilder().Build();
            var secretDescriptors = new List<DaprSecretDescriptor>
            {
                new DaprSecretDescriptor("eshopsecrets")
            };
            config.AddDaprSecretStore("secret-store", secretDescriptors, daprClient);
        })
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

En el ejemplo anterior se carga la `eshopsecrets` colección Secrets en el sistema de configuración de .net en el inicio. El registro del proveedor requiere una instancia de `DaprClient` para invocar la API de Secrets en el sidecar de DAPR. Los demás argumentos incluyen el nombre del almacén secreto y un `DaprSecretDescriptor` objeto con el nombre del secreto.

Una vez cargados, puede recuperar los secretos directamente del código de la aplicación:

```csharp
public void GetCustomer(IConfiguration config)
{
    var connectionString = config["eshopsecrets"]["customerdb"];
}
```

## <a name="secret-store-components"></a>Componentes del almacén secreto

El bloque de creación de secretos admite varios componentes de almacén de secretos. En el momento de la escritura, están disponibles los siguientes almacenes secretos:

- Variables de entorno
- Archivo local
- Secretos de Kubernetes
- Administrador de secretos de AWS
- Azure Key Vault
- Administrador de secretos de GCP
- Almacén de HashiCorp

> [!IMPORTANT]
> Las variables de entorno y los componentes de archivo local están diseñados solo para cargas de trabajo de desarrollo.

En las secciones siguientes se muestra cómo configurar un almacén de secretos.

### <a name="configuration"></a>Configuración

Un almacén de secretos se configura mediante un archivo de configuración de componentes de DAPR. A continuación se muestra la estructura típica del archivo:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: [component name]
  namespace: [namespace]
spec:
  type: secretstores.[secret store type]
  version: [secret store version]
  metadata:
  - name: [property name]
    value: [property value]
```

Todos los archivos de configuración de componentes de DAPR requieren un `name` junto con un `namespace` valor opcional. Además, el `type` campo de la `spec` sección especifica el tipo de componente de almacén secreto. Las propiedades de la `metadata` sección difieren en cada almacén secreto.

### <a name="indirectly-consume-dapr-secrets"></a>Consumo indirecto de secretos de DAPR

Como se mencionó anteriormente en este capítulo, las aplicaciones también pueden consumir secretos haciendo referencia a ellos en archivos de configuración de componentes. Considere la posibilidad de usar un [componente de administración de estado](state-management.md) que use Redis cache para almacenar el estado:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: e$h0p0nD@pr
```

El archivo de configuración anterior contiene una contraseña de **texto no cifrado** para conectarse al servidor de Redis. Las contraseñas **codificadas** siempre son una buena idea. La inserción de este archivo de configuración en un repositorio público expondría la contraseña. El almacenamiento de la contraseña en un almacén secreto mejoraría drásticamente este escenario.

En los siguientes ejemplos se muestra el uso de varios almacenes secretos diferentes.

### <a name="local-file"></a>Archivo local

El componente de archivo local está diseñado para escenarios de desarrollo. Almacena secretos en el sistema de archivos local dentro de un archivo JSON. A continuación se muestra un ejemplo denominado `eshop-secrets.json` . Contiene una contraseña de un solo secreto para Redis:

```json
{
  "eShopRedisPassword": "e$h0p0nD@pr"
}
```

Este archivo se coloca en una `components` carpeta que se especifica al ejecutar la aplicación DAPR.

El siguiente archivo de configuración del almacén secreto utiliza el archivo JSON como almacén secreto. También se coloca en la `components` carpeta:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-local-secret-store
  namespace: eshop
spec:
  type: secretstores.local.file
  version: v1
  metadata:
  - name: secretsFile
    value: ./components/eshop-secrets.json
  - name: nestedSeparator
    value: ":"
```

El tipo de componente es `secretstore.local.file` . El `secretsFile` elemento de metadatos especifica la ruta de acceso al archivo de secretos.

> [!IMPORTANT]
> La ruta de acceso a un archivo de secretos puede ser una ruta de acceso absoluta o relativa. La ruta de acceso relativa se basa en la carpeta en la que se inicia la aplicación. En el ejemplo, la `components` carpeta es una subcarpeta del directorio que contiene la aplicación .net.

En la carpeta de la aplicación, inicie la aplicación DAPR especificando la `components` ruta de acceso como un argumento de línea de comandos:

```console
dapr run --app-id basket-api --components-path ./components dotnet run
```

> [!NOTE]
> Este ejemplo anterior se aplica a la ejecución de DAPR en modo autohospedado. Para el hospedaje de Kubernetes, considere la posibilidad de usar montajes de volumen.

`nestedSeparator`En un archivo de configuración de DAPR se especifica un carácter para *aplanar* una jerarquía JSON. Considere el siguiente fragmento de código:

```json
{
    "redisPassword": "some password",
    "connectionStrings": {
        "customerdb": "some connection string",
        "productdb": "some connection string"
    }
}
```

Si usa un signo de dos puntos como separador, puede recuperar la `customerdb` cadena de conexión mediante la clave `connectionStrings:customerdb` .

> [!NOTE]
> El signo de dos puntos `:` es el valor del separador predeterminado.

En el ejemplo siguiente, un archivo de configuración de administración de estado hace referencia al componente de almacén secreto local para obtener la contraseña para conectarse al servidor de Redis:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    secretKeyRef:
      name: eShopRedisPassword
      key: eShopRedisPassword
auth:
  secretStore: eshop-local-secret-store
```

El `secretKeyRef` elemento hace referencia al secreto que contiene la contraseña. Reemplaza el valor *de texto no cifrado* anterior. El nombre del secreto y el nombre de la clave, `eShopRedisPassword` , hacen referencia al secreto. El nombre del componente de administración de secretos `eshop-local-secret-store` se encuentra en el `auth` elemento de metadatos.

Es posible que se pregunte por qué `eShopRedisPassword` es idéntico para el nombre y la clave en la referencia secreta. En el almacén secreto de archivo local, los secretos no se identifican con un nombre independiente. El escenario será diferente en el ejemplo siguiente con secretos de Kubernetes.

### <a name="kubernetes-secret"></a>Kubernetes secreto

Este segundo ejemplo se centra en una aplicación DAPR que se ejecuta en Kubernetes. Utiliza el mecanismo de secretos estándar que proporciona Kubernetes. Use la CLI de Kubernetes ( `kubectl` ) para crear un secreto denominado `eshop-redis-secret` que contenga la contraseña:

```console
kubectl create secret generic eshopsecrets --from-literal=redisPassword=e$h0p0nD@pr -n eshop
```

Una vez creado, puede hacer referencia al secreto en el archivo de configuración de componentes para la administración de Estados:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: eshopsecrets
      key: redisPassword
auth:
  secretStore: kubernetes
```

El `secretKeyRef` elemento especifica el nombre del secreto de Kubernetes y la clave del secreto, `eshopsecrets` y, `redisPassword` respectivamente. La `auth` sección de metadatos indica a DAPR que use el componente de administración de secretos de Kubernetes.

> [!NOTE]
> Auth es el valor predeterminado cuando se usan secretos de Kubernetes y se puede omitir.

En una configuración de producción, los secretos se crean normalmente como parte de una canalización de CI/CD automatizada. Esto garantiza que solo las personas con permisos suficientes puedan tener acceso a los secretos y cambiarlos. Los desarrolladores crean archivos de configuración sin conocer el valor real de los secretos.

### <a name="azure-key-vault"></a>Azure Key Vault

El ejemplo siguiente está orientado hacia un escenario de producción real. Usa **Azure Key Vault** como almacén secreto. Azure Key Vault es un servicio administrado de Azure que permite almacenar secretos de forma segura en la nube.

Para que este ejemplo funcione, deben cumplirse los siguientes requisitos previos:

- Ha protegido el acceso administrativo a una suscripción de Azure.
- Ha aprovisionado una Azure Key Vault denominada que contiene `eshopkv` un secreto denominado `redisPassword` que contiene la contraseña para conectarse al servidor de Redis.
- Ha creado una [entidad de servicio](/azure/active-directory/develop/howto-create-service-principal-portal) en Azure Active Directory.
- Ha instalado un certificado X509 para esta entidad de servicio (que contiene la clave pública y la clave privada) en el sistema de archivos local.

> [!NOTE]
> Una entidad de servicio es una identidad que una aplicación puede usar para autenticar un servicio de Azure. La entidad de servicio utiliza un certificado X509. La aplicación utiliza este certificado como credencial para autenticarse.

La [documentación de Dapr Azure Key Vault Secret Store](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault/) proporciona instrucciones paso a paso para crear y configurar un entorno de Key Vault.

#### <a name="use-key-vault-when-running-in-self-hosted-mode"></a>Usar Key Vault cuando se ejecuta en modo autohospedado

El consumo de Azure Key Vault en el modo autohospedado de DAPR requiere el siguiente archivo de configuración:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-azurekv-secret-store
  namespace: eshop
spec:
  type: secretstores.azure.keyvault
  version: v1
  metadata:
  - name: vaultName
    value: eshopkv
  - name: spnTenantId
    value: "619926af-a7c3-4e95-93ed-4ecc4e3e652b"
  - name: spnClientId
    value: "6cf48032-6c38-43be-9d6f-2a43ce736b09"
  - name: spnCertificateFile
    value : "azurekv-spn-cert.pfx"
```

El tipo de almacén secreto es `secretstores.azure.keyvault` . El `metadata` elemento para configurar el acceso a Key Vault requiere las siguientes propiedades:

- El `vaultName` contiene el nombre del Azure Key Vault.
- `spnTenantId`Contiene el *identificador de inquilino* de la entidad de servicio utilizada para autenticarse en el Key Vault.
- El `spnClientId` contiene el *identificador* de la aplicación de la entidad de servicio que se usa para autenticarse en el Key Vault.
- `spnCertificateFile`Contiene la ruta de acceso al archivo de certificado de la entidad de servicio para autenticarse en el Key Vault.

> [!TIP]
> Puede copiar la información de la entidad de servicio desde el Azure Portal o CLI de Azure.

Ahora la aplicación puede recuperar la contraseña de Redis desde el Azure Key Vault.

#### <a name="use-key-vault-when-running-on-kubernetes"></a>Usar Key Vault cuando se ejecuta en Kubernetes

El consumo de Azure Key Vault con DAPR y Kubernetes también requiere una entidad de servicio para autenticarse en el Azure Key Vault.

En primer lugar, cree un *secreto de Kubernetes* que contenga un archivo de certificado mediante la herramienta de la CLI de kubectl:

```console
kubectl create secret generic [k8s_spn_secret_name] --from-file=[pfx_certificate_file_local_path] -n eshop
```

El comando requiere dos argumentos de la línea de comandos:

- `[k8s_spn_secret_name]` es el nombre del secreto en el almacén de secretos de Kubernetes.
- `[pfx_certificate_file_local_path]` es la ruta de acceso del archivo de certificado X509.

Una vez creado, puede hacer referencia al secreto de Kubernetes en el archivo de configuración del componente de almacén de secretos:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-azurekv-secret-store
  namespace: eshop
spec:
  type: secretstores.azure.keyvault
  version: v1
  metadata:
  - name: vaultName
    value: [your_keyvault_name]
  - name: spnTenantId
    value: "619926af-a7c3-4e95-93ed-4ecc4e3e652b"
  - name: spnClientId
    value: "6cf48032-6c38-43be-9d6f-2a43ce736b09"
  - name: spnCertificate
    secretKeyRef:
      name: [k8s_spn_secret_name]
      key: [pfx_certificate_file_local_name]
auth:
    secretStore: kubernetes
```

En este momento, una aplicación que se ejecuta en Kubernetes puede recuperar la contraseña de Redis desde el Azure Key Vault.

> [!IMPORTANT]
> Es fundamental mantener el archivo de certificado X509 de la entidad de servicio en un lugar seguro. Es mejor colocarlo en una carpeta conocida fuera del repositorio de código fuente. El archivo de configuración puede hacer referencia al archivo de certificado desde esta carpeta conocida. En una máquina de desarrollo local, es responsable de copiar el certificado en la carpeta. En el caso de las implementaciones automatizadas, la canalización copiará el certificado en el equipo donde se implementa la aplicación. Se recomienda usar una entidad de servicio diferente por entorno. Al hacerlo, se evita que la entidad de servicio de un entorno de desarrollo tenga acceso a los secretos en un entorno de producción.

Cuando se ejecuta en Azure Kubernetes Service (AKS), es preferible usar una [identidad administrada de Azure](/azure/active-directory/managed-identities-azure-resources/overview) para autenticarse en Azure Key Vault. Las identidades administradas están fuera del ámbito de este libro, pero se explican en la documentación de [Azure Key Vault con identidades administradas](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault-managed-identity/) .

### <a name="scope-secrets"></a>Secretos de ámbito

Los ámbitos secretos permiten controlar los secretos a los que puede tener acceso la aplicación. Los ámbitos se configuran en un archivo de configuración de DAPR sidecar. La [documentación de configuración de DAPR](https://docs.dapr.io/operations/configuration/configuration-overview/) proporciona instrucciones para el ámbito de los secretos.

A continuación se muestra un ejemplo de un archivo de configuración de DAPR sidecar que contiene ámbitos secretos:

```yml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: dapr-config
  namespace: eshop
spec:
  tracing:
    samplingRate: "1"
  secrets:
    scopes:
      - storeName: eshop-azurekv-secret-store
        defaultAccess: allow
        deniedSecrets: ["redisPassword", "apiKey"]
```

Especifique los ámbitos por almacén secreto. En el ejemplo anterior, el almacén de secretos se denomina `eshop-azurekv-secret-store` . Configure el acceso a los secretos con las siguientes propiedades:

| Propiedad         | Valor               | Descripción                                                                                                                       |
|------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| `defaultAccess`  | `allow` o `deny`   | Permite o deniega el acceso a *todos los* secretos del almacén secreto especificado. Esta propiedad es opcional y su valor predeterminado es `allow` . |
| `allowedSecrets` | Lista de claves secretas | Se podrá acceder a los secretos especificados en la matriz. Esta propiedad es opcional.                                                     |
| `deniedSecrets`  | Lista de claves secretas | NO se podrá acceder a los secretos especificados en la matriz. Esta propiedad es opcional.                                                 |

Las `allowedSecrets` `deniedSecrets` propiedades y tienen prioridad sobre la `defaultAccess` propiedad. Imagine que especifica `defaultAccess: allowed` y una `allowedSecrets` lista. En este caso, `allowedSecrets` la aplicación solo podrá tener acceso a los secretos de la lista.

## <a name="reference-application-eshopondapr"></a>Aplicación de referencia: eShopOnDapr

La aplicación de referencia eShopOnDapr usa el bloque de creación de secretos para dos secretos:

- La contraseña para conectarse a la caché en Redis.
- La clave de API para usar la API de Twilio Sendgrid. La aplicación usa Twillio para enviar correos electrónicos mediante un enlace de salida de DAPR (como se describe en el capítulo sobre los [enlaces de bloques de creación](bindings.md)).

Al ejecutar la aplicación mediante Docker Compose, se usa el almacén de secreto de **archivo local** . El archivo de configuración de componentes `eshop-secretstore.yaml` se encuentra en la `dapr/components` carpeta del repositorio eShopOnDapr:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-secretstore
  namespace: eshop
spec:
  type: secretstores.local.file
  version: v1
  metadata:
  - name: secretsFile
    value: ./components/eshop-secretstore.json
```

El archivo de configuración hace referencia al archivo de almacenamiento local que se `eshop-secretstore.json` encuentra en la misma carpeta:

```json
{
    "redisPassword": "**********",
    "sendgridAPIKey": "**********"
}
```

La `components` carpeta se especifica en la línea de comandos y se monta como una carpeta local dentro del contenedor de DAPR sidecar. A continuación se muestra un fragmento de código del `docker-compose.override.yml` archivo en la raíz del repositorio que especifica el montaje del volumen:

```yaml
  ordering-backgroundtasks-dapr:
    command: ["./daprd",
      "-app-id", "ordering-backgroundtasks",
      "-app-port", "80",
      "-dapr-grpc-port", "50004",
      "-components-path", "/components",
      "-config", "/configuration/eshop-config.yaml"
      ]
    volumes:
      - "./dapr/components/:/components"
      - "./dapr/configuration/:/configuration"
```

> [!NOTE]
> El archivo de invalidación de Docker Compose contiene valores de configuración específicos del entorno.

El `/components` montaje del volumen y el `--components-path` argumento de la línea de comandos se pasan al `daprd` comando de inicio.

Una vez configurado, otros archivos de configuración de componentes también pueden hacer referencia a los secretos. A continuación se muestra un ejemplo de la configuración del componente de publicación/suscripción que consume secretos:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub
  namespace: eshop
spec:
  type: pubsub.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: redisPassword
auth:
  secretStore: eshop-secretstore
```

En el ejemplo anterior, el almacén de Redis local se usa para hacer referencia a los secretos.

## <a name="summary"></a>Resumen

El bloque de creación de secretos de DAPR proporciona funciones para almacenar y recuperar valores de configuración confidenciales como contraseñas y cadenas de conexión. Mantiene secretos privados y evita que se revelen accidentalmente.

El bloque de creación admite varios almacenes secretos diferentes y oculta su complejidad con la API DAPR Secrets.

El SDK de .NET para DAPR proporciona un `DaprClient` objeto para recuperar los secretos. También incluye un proveedor de configuración de .NET que agrega secretos al sistema de configuración de .NET Core. Una vez cargados, puede consumir estos secretos en el código .NET.

Puede usar ámbitos secretos para controlar el acceso a secretos específicos.

## <a name="references"></a>Referencias

- [Más allá de la aplicación Twelve-Factor](https://tanzu.vmware.com/content/blog/beyond-the-twelve-factor-app)

>[!div class="step-by-step"]
>[Anterior](observability.md)
>[Siguiente](summary.md)
