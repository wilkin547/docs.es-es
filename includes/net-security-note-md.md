> [!CAUTION]
>  Seguridad de acceso del código y código de confianza parcial  
>   
>  .NET Framework proporciona seguridad de acceso del código (CAS), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.  La seguridad de acceso de código de .NET Framework no debería usarse como mecanismo para reforzar los límites de seguridad basados en el origen del código u otros aspectos de identidad. Estamos actualizando las guías para reflejar que la seguridad de acceso de código y el código transparente de seguridad no se podrán usar como límites de seguridad con código de confianza parcial, especialmente en código con orígenes desconocidos. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.  
>   
>  Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.