---
title: Implementación de binarios de trabajo y función definida por el usuario de .NET para Apache Spark
description: Aprenda a implementar binarios de trabajo y función definida por el usuario de .NET para Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: c777fdb26045c62317b49259fdde974f43ba5c0d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293772"
---
# <a name="deploy-net-for-apache-spark-worker-and-user-defined-function-binaries"></a>Implementación de binarios de trabajo y función definida por el usuario de .NET para Apache Spark

En este artículo de procedimientos se proporcionan instrucciones generales sobre cómo implementar binarios de trabajo y función definida por el usuario de .NET para Apache Spark. Se conocen las variables de entorno que se van a configurar, así como algunos parámetros de uso común para iniciar aplicaciones con `spark-submit`.

## <a name="configurations"></a>Configuraciones

Las configuraciones muestran las variables de entorno generales y la configuración de parámetros para implementar los binarios de trabajo y función definida por el usuario de .NET para Apache Spark.

### <a name="environment-variables"></a>Variables de entorno

Al implementar trabajos y escribir UDF, hay algunas variables de entorno de uso común que puede que tenga que establecer:

| Variable de entorno         | Descripción
| :--------------------------- | :----------
| DOTNET_WORKER_DIR            | Ruta de acceso donde se ha generado el binario de <code>Microsoft.Spark.Worker</code>.</br>La usa el controlador de Spark y se pasa a los ejecutores de Spark. Si esta variable no está configurada, los ejecutores de Spark buscan la ruta de acceso especificada en la variable de entorno <code>PATH</code>.</br>_Por ejemplo, "C:\bin\Microsoft.Spark.Worker"_
| DOTNET_ASSEMBLY_SEARCH_PATHS | Rutas de acceso separadas por comas donde <code>Microsoft.Spark.Worker</code> va a cargar los ensamblados.</br>Tenga en cuenta que si una ruta de acceso comienza por ".", el directorio de trabajo se antepone. Si está en **modo Yarn**, "." representaría el directorio de trabajo del contenedor.</br>_Por ejemplo, "C:\Users\\&lt;nombre de usuario&gt;\\&lt;miaplicaciónspark&gt;\bin\Debug\\&lt;versión de dotnet&gt;"_
| DOTNET_WORKER_DEBUG          | Si quiere <a href="https://github.com/dotnet/spark/blob/master/docs/developer-guide.md#debugging-user-defined-function-udf">depurar una UDF</a>, establezca esta variable de entorno en <code>1</code> antes de ejecutar <code>spark-submit</code>.

### <a name="parameter-options"></a>Opciones de parámetros

Una vez que la aplicación Spark está [agrupada](https://spark.apache.org/docs/latest/submitting-applications.html#bundling-your-applications-dependencies), puede iniciarla mediante `spark-submit`. En la tabla siguiente se muestran algunas opciones usadas frecuentemente:

| Nombre de parámetro        | Descripción
| :---------------------| :----------
| --class               | Punto de entrada de la aplicación.</br>_Por ejemplo, org.apache.spark.deploy.dotnet.DotnetRunner_
| --master              | <a href="https://spark.apache.org/docs/latest/submitting-applications.html#master-urls">Dirección URL principal</a> del clúster.</br>_Por ejemplo, yarn_
| --deploy-mode         | Si se va a implementar el controlador en los nodos de trabajo (<code>cluster</code>) o localmente como un cliente externo (<code>client</code>).</br>Valor predeterminado: <code>client</code>
| --conf                | Propiedad de configuración arbitraria de Spark en formato <code>key=value</code>.</br>_Por ejemplo, spark.yarn.appMasterEnv.DOTNET_WORKER_DIR=.\worker\Microsoft.Spark.Worker_
| --files               | Lista separada por comas de archivos que se van a colocar en el directorio de trabajo de cada ejecutor.<br/><ul><li>Tenga en cuenta que esta opción solo se aplica al modo Yarn.</li><li>Admite la especificación de nombres de archivo con # de forma similar a Hadoop.</br></ul>_Por ejemplo, <code>myLocalSparkApp.dll#appSeen.dll</code>. La aplicación debe usar el nombre como <code>appSeen.dll</code> para hacer referencia a <code>myLocalSparkApp.dll</code> al ejecutarse en YARN._</li>
| --archives          | Lista separada por comas de archivos que se van a extraer en el directorio de trabajo de cada ejecutor.</br><ul><li>Tenga en cuenta que esta opción solo se aplica al modo Yarn.</li><li>Admite la especificación de nombres de archivo con # de forma similar a Hadoop.</br></ul>_Por ejemplo, <code>hdfs://&lt;path to your worker file&gt;/Microsoft.Spark.Worker.zip#worker</code>. Esto copia y extrae el archivo zip en la carpeta <code>worker</code>._</li>
| application-jar       | Ruta de acceso a un archivo jar agrupado que incluye la aplicación y todas las dependencias.</br>_Por ejemplo, hdfs://&lt;ruta de acceso al archivo jar&gt;/microsoft-spark-&lt;versión&gt;.jar_
| application-arguments | Argumentos pasados al método principal de la clase principal, si la hubiera.</br>_Por ejemplo, hdfs://&lt;ruta de acceso a la aplicación&gt;/&lt;la aplicación&gt;.zip &lt;nombre de la aplicación&gt; &lt;argumentos de la aplicación&gt;_

> [!NOTE]
> Especifique todos los elementos `--options` antes de `application-jar` al iniciar aplicaciones con `spark-submit`; de lo contrario, se omiten. Para obtener más información, vea [Opciones de `spark-submit`](https://spark.apache.org/docs/latest/submitting-applications.html) y [Detalles para ejecutar Spark en YARN](https://spark.apache.org/docs/latest/running-on-yarn.html).

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="when-i-run-a-spark-app-with-udfs-i-get-a-filenotfoundexception-error-what-should-i-do"></a>Cuando ejecuto una aplicación de Spark con UDF, obtengo un error "FileNotFoundException". ¿Qué debo hacer?

> **Error:** [Error] [TaskRunner] [0] Error de ProcessStream() con la excepción: System.IO.FileNotFoundException: Ensamblado 'mySparkApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null' Archivo no encontrado: 'mySparkApp.dll'

**Respuesta:** Compruebe que la variable de entorno `DOTNET_ASSEMBLY_SEARCH_PATHS` se ha establecido correctamente. Debe ser la ruta de acceso que contiene `mySparkApp.dll`.

### <a name="after-i-upgraded-my-net-for-apache-spark-version-and-reset-the-dotnet_worker_dir-environment-variable-why-do-i-still-get-the-following-ioexception-error"></a>Después de actualizar la versión de .NET para Apache Spark y restablecer la variable de entorno `DOTNET_WORKER_DIR`, ¿por qué sigue apareciendo el siguiente error `IOException`?

> **Error:** Tarea perdida 0.0 en fase 11.0 (TID 24, localhost, executor driver): java.io.IOException: No se puede ejecutar el programa "Microsoft.Spark.Worker.exe": CreateProcess error=2, No se puede encontrar el archivo especificado.

**Respuesta:** Primero pruebe a reiniciar la ventana de PowerShell (u otras ventanas de comandos) para que pueda tomar los valores de las variables de entorno más recientes. Luego inicie el programa.

### <a name="after-submitting-my-spark-application-i-get-the-error-systemtypeloadexception-could-not-load-type-systemruntimeremotingcontextscontext"></a>Después de enviar la aplicación de Spark, obtengo el error `System.TypeLoadException: Could not load type 'System.Runtime.Remoting.Contexts.Context'`.

> **Error:** [Error] [TaskRunner] [0] Error de ProcessStream() con la excepción: System.TypeLoadException: No se pudo cargar el tipo 'System.Runtime.Remoting.Contexts.Context' del ensamblado 'mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=...'.

**Respuesta:** Compruebe la versión de `Microsoft.Spark.Worker` que está usando. Hay dos versiones: **.NET Framework 4.6.1** y **.NET Core 3.1.x**. En este caso, se debe usar `Microsoft.Spark.Worker.net461.win-x64-<version>` (que puede [descargar](https://github.com/dotnet/spark/releases)), ya que `System.Runtime.Remoting.Contexts.Context` solo es para .NET Framework.

### <a name="how-do-i-run-my-spark-application-with-udfs-on-yarn-which-environment-variables-and-parameters-should-i-use"></a>¿Cómo ejecuto la aplicación de Spark con UDF en YARN? ¿Qué variables de entorno y parámetros debo usar?

**Respuesta:** Para iniciar la aplicación de Spark en YARN, las variables de entorno deben especificarse como `spark.yarn.appMasterEnv.[EnvironmentVariableName]`. Vea a continuación un ejemplo con `spark-submit`:

```powershell
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master yarn \
--deploy-mode cluster \
--conf spark.yarn.appMasterEnv.DOTNET_WORKER_DIR=./worker/Microsoft.Spark.Worker-<version> \
--conf spark.yarn.appMasterEnv.DOTNET_ASSEMBLY_SEARCH_PATHS=./udfs \
--archives hdfs://<path to your files>/Microsoft.Spark.Worker.net461.win-x64-<version>.zip#worker,hdfs://<path to your files>/mySparkApp.zip#udfs \
hdfs://<path to jar file>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
hdfs://<path to your files>/mySparkApp.zip mySparkApp
```

## <a name="next-steps"></a>Pasos siguientes

* [Introducción a .NET para Apache Spark](../tutorials/get-started.md)
* [Depuración de una aplicación de .NET para Apache Spark en Windows](debug.md)
