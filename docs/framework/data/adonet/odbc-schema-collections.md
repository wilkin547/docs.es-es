---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43750014"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="d8e7b-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="d8e7b-102">ODBC Schema Collections</span></span>
<span data-ttu-id="d8e7b-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="d8e7b-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="d8e7b-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8e7b-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="d8e7b-105">El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="d8e7b-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d8e7b-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-106">Tables</span></span>  
  
-   <span data-ttu-id="d8e7b-107">Índices</span><span class="sxs-lookup"><span data-stu-id="d8e7b-107">Indexes</span></span>  
  
-   <span data-ttu-id="d8e7b-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-108">Columns</span></span>  
  
-   <span data-ttu-id="d8e7b-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8e7b-109">Procedures</span></span>  
  
-   <span data-ttu-id="d8e7b-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8e7b-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d8e7b-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8e7b-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d8e7b-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="d8e7b-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-113">Tables and Views</span></span>  
  
|<span data-ttu-id="d8e7b-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-114">ColumnName</span></span>|<span data-ttu-id="d8e7b-115">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d8e7b-116">TABLE_CAT</span></span>|<span data-ttu-id="d8e7b-117">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-117">String</span></span>|  
|<span data-ttu-id="d8e7b-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d8e7b-118">TABLE_SCHEM</span></span>|<span data-ttu-id="d8e7b-119">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-119">String</span></span>|  
|<span data-ttu-id="d8e7b-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-120">TABLE_NAME</span></span>|<span data-ttu-id="d8e7b-121">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-121">String</span></span>|  
|<span data-ttu-id="d8e7b-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-122">TABLE_TYPE</span></span>|<span data-ttu-id="d8e7b-123">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-123">String</span></span>|  
|<span data-ttu-id="d8e7b-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-124">REMARKS</span></span>|<span data-ttu-id="d8e7b-125">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d8e7b-126">Índices</span><span class="sxs-lookup"><span data-stu-id="d8e7b-126">Indexes</span></span>  
  
|<span data-ttu-id="d8e7b-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-127">ColumnName</span></span>|<span data-ttu-id="d8e7b-128">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d8e7b-129">TABLE_CAT</span></span>|<span data-ttu-id="d8e7b-130">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-130">String</span></span>|  
|<span data-ttu-id="d8e7b-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d8e7b-131">TABLE_SCHEM</span></span>|<span data-ttu-id="d8e7b-132">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-132">String</span></span>|  
|<span data-ttu-id="d8e7b-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-133">TABLE_NAME</span></span>|<span data-ttu-id="d8e7b-134">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-134">String</span></span>|  
|<span data-ttu-id="d8e7b-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-135">NON_UNIQUE</span></span>|<span data-ttu-id="d8e7b-136">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-136">Int16</span></span>|  
|<span data-ttu-id="d8e7b-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-138">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-138">String</span></span>|  
|<span data-ttu-id="d8e7b-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-139">INDEX_NAME</span></span>|<span data-ttu-id="d8e7b-140">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-140">String</span></span>|  
|<span data-ttu-id="d8e7b-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-141">TYPE</span></span>|<span data-ttu-id="d8e7b-142">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-142">Int16</span></span>|  
|<span data-ttu-id="d8e7b-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-144">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-144">Int16</span></span>|  
|<span data-ttu-id="d8e7b-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-145">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-146">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-146">String</span></span>|  
|<span data-ttu-id="d8e7b-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="d8e7b-147">ASC_OR_DESC</span></span>|<span data-ttu-id="d8e7b-148">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-148">String</span></span>|  
|<span data-ttu-id="d8e7b-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="d8e7b-149">CARDINATLITY</span></span>|<span data-ttu-id="d8e7b-150">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-150">Int32</span></span>|  
|<span data-ttu-id="d8e7b-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="d8e7b-151">PAGES</span></span>|<span data-ttu-id="d8e7b-152">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-152">Int32</span></span>|  
|<span data-ttu-id="d8e7b-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-153">FILTER_CONDITION</span></span>|<span data-ttu-id="d8e7b-154">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-154">String</span></span>|  
|<span data-ttu-id="d8e7b-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8e7b-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d8e7b-156">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-156">String</span></span>|  
|<span data-ttu-id="d8e7b-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-158">Byte</span><span class="sxs-lookup"><span data-stu-id="d8e7b-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d8e7b-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-159">Columns</span></span>  
  
|<span data-ttu-id="d8e7b-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-160">ColumnName</span></span>|<span data-ttu-id="d8e7b-161">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d8e7b-162">TABLE_CAT</span></span>|<span data-ttu-id="d8e7b-163">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-163">String</span></span>|  
|<span data-ttu-id="d8e7b-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d8e7b-164">TABLE_SCHEM</span></span>|<span data-ttu-id="d8e7b-165">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-165">String</span></span>|  
|<span data-ttu-id="d8e7b-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-166">TABLE_NAME</span></span>|<span data-ttu-id="d8e7b-167">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-167">String</span></span>|  
|<span data-ttu-id="d8e7b-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-168">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-169">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-169">String</span></span>|  
|<span data-ttu-id="d8e7b-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-170">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-171">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-171">Int16</span></span>|  
|<span data-ttu-id="d8e7b-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-172">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-173">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-173">String</span></span>|  
|<span data-ttu-id="d8e7b-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-174">COLUMN_SIZE</span></span>|<span data-ttu-id="d8e7b-175">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-175">Int32</span></span>|  
|<span data-ttu-id="d8e7b-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="d8e7b-177">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-177">Int32</span></span>|  
|<span data-ttu-id="d8e7b-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d8e7b-179">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-179">Int16</span></span>|  
|<span data-ttu-id="d8e7b-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d8e7b-181">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-181">Int16</span></span>|  
|<span data-ttu-id="d8e7b-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-182">NULLABLE</span></span>|<span data-ttu-id="d8e7b-183">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-183">Int16</span></span>|  
|<span data-ttu-id="d8e7b-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-184">REMARKS</span></span>|<span data-ttu-id="d8e7b-185">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-185">String</span></span>|  
|<span data-ttu-id="d8e7b-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d8e7b-186">COLUMN_DEF</span></span>|<span data-ttu-id="d8e7b-187">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-187">String</span></span>|  
|<span data-ttu-id="d8e7b-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-189">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-189">Int16</span></span>|  
|<span data-ttu-id="d8e7b-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d8e7b-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d8e7b-191">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-191">Int16</span></span>|  
|<span data-ttu-id="d8e7b-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d8e7b-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-193">Int32</span></span>|  
|<span data-ttu-id="d8e7b-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-195">Int32</span></span>|  
|<span data-ttu-id="d8e7b-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-196">IS_NULLABLE</span></span>|<span data-ttu-id="d8e7b-197">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-197">String</span></span>|  
|<span data-ttu-id="d8e7b-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8e7b-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d8e7b-199">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-199">String</span></span>|  
|<span data-ttu-id="d8e7b-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8e7b-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d8e7b-201">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-201">String</span></span>|  
|<span data-ttu-id="d8e7b-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-203">Byte</span><span class="sxs-lookup"><span data-stu-id="d8e7b-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d8e7b-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8e7b-204">Procedures</span></span>  
  
|<span data-ttu-id="d8e7b-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-205">ColumnName</span></span>|<span data-ttu-id="d8e7b-206">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d8e7b-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="d8e7b-208">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-208">String</span></span>|  
|<span data-ttu-id="d8e7b-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d8e7b-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d8e7b-210">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-210">String</span></span>|  
|<span data-ttu-id="d8e7b-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-212">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-212">String</span></span>|  
|<span data-ttu-id="d8e7b-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d8e7b-214">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-214">Int32</span></span>|  
|<span data-ttu-id="d8e7b-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d8e7b-216">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-216">Int32</span></span>|  
|<span data-ttu-id="d8e7b-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d8e7b-218">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-218">Int32</span></span>|  
|<span data-ttu-id="d8e7b-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-219">REMARKS</span></span>|<span data-ttu-id="d8e7b-220">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-220">String</span></span>|  
|<span data-ttu-id="d8e7b-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d8e7b-222">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d8e7b-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8e7b-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d8e7b-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-224">ColumnName</span></span>|<span data-ttu-id="d8e7b-225">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d8e7b-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="d8e7b-227">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-227">String</span></span>|  
|<span data-ttu-id="d8e7b-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d8e7b-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d8e7b-229">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-229">String</span></span>|  
|<span data-ttu-id="d8e7b-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-231">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-231">String</span></span>|  
|<span data-ttu-id="d8e7b-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-232">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-233">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-233">String</span></span>|  
|<span data-ttu-id="d8e7b-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-234">COLUMN_TYPE</span></span>|<span data-ttu-id="d8e7b-235">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-235">Int16</span></span>|  
|<span data-ttu-id="d8e7b-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-236">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-237">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-237">Int16</span></span>|  
|<span data-ttu-id="d8e7b-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-238">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-239">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-239">String</span></span>|  
|<span data-ttu-id="d8e7b-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-240">COLUMN_SIZE</span></span>|<span data-ttu-id="d8e7b-241">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-241">Int32</span></span>|  
|<span data-ttu-id="d8e7b-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="d8e7b-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-243">Int32</span></span>|  
|<span data-ttu-id="d8e7b-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d8e7b-245">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-245">Int16</span></span>|  
|<span data-ttu-id="d8e7b-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d8e7b-247">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-247">Int16</span></span>|  
|<span data-ttu-id="d8e7b-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-248">NULLABLE</span></span>|<span data-ttu-id="d8e7b-249">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-249">Int16</span></span>|  
|<span data-ttu-id="d8e7b-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-250">REMARKS</span></span>|<span data-ttu-id="d8e7b-251">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-251">String</span></span>|  
|<span data-ttu-id="d8e7b-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d8e7b-252">COLUMN_DEF</span></span>|<span data-ttu-id="d8e7b-253">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-253">String</span></span>|  
|<span data-ttu-id="d8e7b-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-255">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-255">Int16</span></span>|  
|<span data-ttu-id="d8e7b-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d8e7b-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d8e7b-257">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-257">Int16</span></span>|  
|<span data-ttu-id="d8e7b-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d8e7b-259">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-259">Int32</span></span>|  
|<span data-ttu-id="d8e7b-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-261">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-261">Int32</span></span>|  
|<span data-ttu-id="d8e7b-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-262">IS_NULLABLE</span></span>|<span data-ttu-id="d8e7b-263">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-263">String</span></span>|  
|<span data-ttu-id="d8e7b-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8e7b-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d8e7b-265">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-265">String</span></span>|  
|<span data-ttu-id="d8e7b-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8e7b-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d8e7b-267">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-267">String</span></span>|  
|<span data-ttu-id="d8e7b-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-269">Byte</span><span class="sxs-lookup"><span data-stu-id="d8e7b-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d8e7b-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8e7b-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d8e7b-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-271">ColumnName</span></span>|<span data-ttu-id="d8e7b-272">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d8e7b-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="d8e7b-274">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-274">String</span></span>|  
|<span data-ttu-id="d8e7b-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d8e7b-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d8e7b-276">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-276">String</span></span>|  
|<span data-ttu-id="d8e7b-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-278">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-278">String</span></span>|  
|<span data-ttu-id="d8e7b-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-279">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-280">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-280">String</span></span>|  
|<span data-ttu-id="d8e7b-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-281">COLUMN_TYPE</span></span>|<span data-ttu-id="d8e7b-282">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-282">Int16</span></span>|  
|<span data-ttu-id="d8e7b-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-283">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-284">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-284">Int16</span></span>|  
|<span data-ttu-id="d8e7b-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-285">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-286">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-286">String</span></span>|  
|<span data-ttu-id="d8e7b-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-287">COLUMN_SIZE</span></span>|<span data-ttu-id="d8e7b-288">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-288">Int32</span></span>|  
|<span data-ttu-id="d8e7b-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="d8e7b-290">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-290">Int32</span></span>|  
|<span data-ttu-id="d8e7b-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d8e7b-292">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-292">Int16</span></span>|  
|<span data-ttu-id="d8e7b-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d8e7b-294">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-294">Int16</span></span>|  
|<span data-ttu-id="d8e7b-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-295">NULLABLE</span></span>|<span data-ttu-id="d8e7b-296">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-296">Int16</span></span>|  
|<span data-ttu-id="d8e7b-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-297">REMARKS</span></span>|<span data-ttu-id="d8e7b-298">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-298">String</span></span>|  
|<span data-ttu-id="d8e7b-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d8e7b-299">COLUMN_DEF</span></span>|<span data-ttu-id="d8e7b-300">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-300">String</span></span>|  
|<span data-ttu-id="d8e7b-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-302">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-302">Int16</span></span>|  
|<span data-ttu-id="d8e7b-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d8e7b-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d8e7b-304">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-304">Int16</span></span>|  
|<span data-ttu-id="d8e7b-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d8e7b-306">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-306">Int32</span></span>|  
|<span data-ttu-id="d8e7b-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-308">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-308">Int32</span></span>|  
|<span data-ttu-id="d8e7b-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-309">IS_NULLABLE</span></span>|<span data-ttu-id="d8e7b-310">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-310">String</span></span>|  
|<span data-ttu-id="d8e7b-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8e7b-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d8e7b-312">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-312">String</span></span>|  
|<span data-ttu-id="d8e7b-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8e7b-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d8e7b-314">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-314">String</span></span>|  
|<span data-ttu-id="d8e7b-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-316">Byte</span><span class="sxs-lookup"><span data-stu-id="d8e7b-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="d8e7b-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8e7b-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="d8e7b-318">El controlador ODBC de Oracle de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="d8e7b-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d8e7b-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-319">Tables</span></span>  
  
-   <span data-ttu-id="d8e7b-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-320">Columns</span></span>  
  
-   <span data-ttu-id="d8e7b-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8e7b-321">Procedures</span></span>  
  
-   <span data-ttu-id="d8e7b-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8e7b-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d8e7b-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8e7b-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d8e7b-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-324">Views</span></span>  
  
-   <span data-ttu-id="d8e7b-325">Índices</span><span class="sxs-lookup"><span data-stu-id="d8e7b-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="d8e7b-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-326">Tables and Views</span></span>  
  
|<span data-ttu-id="d8e7b-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-327">ColumnName</span></span>|<span data-ttu-id="d8e7b-328">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-330">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-330">String</span></span>|  
|<span data-ttu-id="d8e7b-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-331">TABLE_OWNER</span></span>|<span data-ttu-id="d8e7b-332">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-332">String</span></span>|  
|<span data-ttu-id="d8e7b-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-333">TABLE_NAME</span></span>|<span data-ttu-id="d8e7b-334">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-334">String</span></span>|  
|<span data-ttu-id="d8e7b-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-335">TABLE_TYPE</span></span>|<span data-ttu-id="d8e7b-336">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-336">String</span></span>|  
|<span data-ttu-id="d8e7b-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-337">REMARKS</span></span>|<span data-ttu-id="d8e7b-338">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d8e7b-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-339">Columns</span></span>  
  
|<span data-ttu-id="d8e7b-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-340">ColumnName</span></span>|<span data-ttu-id="d8e7b-341">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-343">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-343">String</span></span>|  
|<span data-ttu-id="d8e7b-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-344">TABLE_OWNER</span></span>|<span data-ttu-id="d8e7b-345">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-345">String</span></span>|  
|<span data-ttu-id="d8e7b-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-346">TABLE_NAME</span></span>|<span data-ttu-id="d8e7b-347">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-347">String</span></span>|  
|<span data-ttu-id="d8e7b-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-348">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-349">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-349">String</span></span>|  
|<span data-ttu-id="d8e7b-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-350">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-351">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-351">Int16</span></span>|  
|<span data-ttu-id="d8e7b-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-352">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-353">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-353">String</span></span>|  
|<span data-ttu-id="d8e7b-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-354">PRECISION</span></span>|<span data-ttu-id="d8e7b-355">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-355">Int32</span></span>|  
|<span data-ttu-id="d8e7b-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-356">LENGTH</span></span>|<span data-ttu-id="d8e7b-357">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-357">Int32</span></span>|  
|<span data-ttu-id="d8e7b-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-358">SCALE</span></span>|<span data-ttu-id="d8e7b-359">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-359">Int16</span></span>|  
|<span data-ttu-id="d8e7b-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-360">RADIX</span></span>|<span data-ttu-id="d8e7b-361">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-361">Int16</span></span>|  
|<span data-ttu-id="d8e7b-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-362">NULLABLE</span></span>|<span data-ttu-id="d8e7b-363">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-363">Int16</span></span>|  
|<span data-ttu-id="d8e7b-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-364">REMARKS</span></span>|<span data-ttu-id="d8e7b-365">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-365">String</span></span>|  
|<span data-ttu-id="d8e7b-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-367">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d8e7b-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8e7b-368">Procedures</span></span>  
  
|<span data-ttu-id="d8e7b-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-369">ColumnName</span></span>|<span data-ttu-id="d8e7b-370">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-372">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-372">String</span></span>|  
|<span data-ttu-id="d8e7b-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d8e7b-374">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-374">String</span></span>|  
|<span data-ttu-id="d8e7b-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-376">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-376">String</span></span>|  
|<span data-ttu-id="d8e7b-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d8e7b-378">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-378">Int16</span></span>|  
|<span data-ttu-id="d8e7b-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d8e7b-380">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-380">Int16</span></span>|  
|<span data-ttu-id="d8e7b-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d8e7b-382">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-382">Int16</span></span>|  
|<span data-ttu-id="d8e7b-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-383">REMARKS</span></span>|<span data-ttu-id="d8e7b-384">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-384">String</span></span>|  
|<span data-ttu-id="d8e7b-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d8e7b-386">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d8e7b-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8e7b-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d8e7b-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-388">ColumnName</span></span>|<span data-ttu-id="d8e7b-389">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-391">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-391">String</span></span>|  
|<span data-ttu-id="d8e7b-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d8e7b-393">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-393">String</span></span>|  
|<span data-ttu-id="d8e7b-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-395">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-395">String</span></span>|  
|<span data-ttu-id="d8e7b-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-396">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-397">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-397">String</span></span>|  
|<span data-ttu-id="d8e7b-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-398">COLUMN_TYPE</span></span>|<span data-ttu-id="d8e7b-399">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-399">Int16</span></span>|  
|<span data-ttu-id="d8e7b-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-400">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-401">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-401">Int16</span></span>|  
|<span data-ttu-id="d8e7b-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-402">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-403">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-403">String</span></span>|  
|<span data-ttu-id="d8e7b-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-404">PRECISION</span></span>|<span data-ttu-id="d8e7b-405">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-405">Int32</span></span>|  
|<span data-ttu-id="d8e7b-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-406">LENGTH</span></span>|<span data-ttu-id="d8e7b-407">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-407">Int32</span></span>|  
|<span data-ttu-id="d8e7b-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-408">SCALE</span></span>|<span data-ttu-id="d8e7b-409">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-409">Int16</span></span>|  
|<span data-ttu-id="d8e7b-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-410">RADIX</span></span>|<span data-ttu-id="d8e7b-411">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-411">Int16</span></span>|  
|<span data-ttu-id="d8e7b-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-412">NULLABLE</span></span>|<span data-ttu-id="d8e7b-413">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-413">Int16</span></span>|  
|<span data-ttu-id="d8e7b-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-414">REMARKS</span></span>|<span data-ttu-id="d8e7b-415">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-415">String</span></span>|  
|<span data-ttu-id="d8e7b-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d8e7b-416">OVERLOAD</span></span>|<span data-ttu-id="d8e7b-417">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-417">Int32</span></span>|  
|<span data-ttu-id="d8e7b-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-419">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="d8e7b-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="d8e7b-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="d8e7b-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="d8e7b-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d8e7b-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-422">Tables</span></span>  
  
-   <span data-ttu-id="d8e7b-423">Índices</span><span class="sxs-lookup"><span data-stu-id="d8e7b-423">Indexes</span></span>  
  
-   <span data-ttu-id="d8e7b-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-424">Columns</span></span>  
  
-   <span data-ttu-id="d8e7b-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8e7b-425">Procedures</span></span>  
  
-   <span data-ttu-id="d8e7b-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8e7b-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d8e7b-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8e7b-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d8e7b-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="d8e7b-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-429">Tables and Views</span></span>  
  
|<span data-ttu-id="d8e7b-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-430">ColumnName</span></span>|<span data-ttu-id="d8e7b-431">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-433">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-433">String</span></span>|  
|<span data-ttu-id="d8e7b-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-434">TABLE_OWNER</span></span>|<span data-ttu-id="d8e7b-435">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-435">String</span></span>|  
|<span data-ttu-id="d8e7b-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-436">TABLE_NAME</span></span>|<span data-ttu-id="d8e7b-437">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-437">String</span></span>|  
|<span data-ttu-id="d8e7b-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-438">TABLE_TYPE</span></span>|<span data-ttu-id="d8e7b-439">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-439">String</span></span>|  
|<span data-ttu-id="d8e7b-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-440">REMARKS</span></span>|<span data-ttu-id="d8e7b-441">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d8e7b-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8e7b-442">Columns</span></span>  
  
|<span data-ttu-id="d8e7b-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-443">ColumnName</span></span>|<span data-ttu-id="d8e7b-444">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-446">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-446">String</span></span>|  
|<span data-ttu-id="d8e7b-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-447">TABLE_OWNER</span></span>|<span data-ttu-id="d8e7b-448">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-448">String</span></span>|  
|<span data-ttu-id="d8e7b-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-449">TABLE_NAME</span></span>|<span data-ttu-id="d8e7b-450">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-450">String</span></span>|  
|<span data-ttu-id="d8e7b-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-451">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-452">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-452">String</span></span>|  
|<span data-ttu-id="d8e7b-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-453">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-454">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-454">Int16</span></span>|  
|<span data-ttu-id="d8e7b-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-455">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-456">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-456">String</span></span>|  
|<span data-ttu-id="d8e7b-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-457">PRECISION</span></span>|<span data-ttu-id="d8e7b-458">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-458">Int32</span></span>|  
|<span data-ttu-id="d8e7b-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-459">LENGTH</span></span>|<span data-ttu-id="d8e7b-460">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-460">Int32</span></span>|  
|<span data-ttu-id="d8e7b-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-461">SCALE</span></span>|<span data-ttu-id="d8e7b-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-462">Int16</span></span>|  
|<span data-ttu-id="d8e7b-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-463">RADIX</span></span>|<span data-ttu-id="d8e7b-464">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-464">Int16</span></span>|  
|<span data-ttu-id="d8e7b-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-465">NULLABLE</span></span>|<span data-ttu-id="d8e7b-466">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-466">Int16</span></span>|  
|<span data-ttu-id="d8e7b-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-467">REMARKS</span></span>|<span data-ttu-id="d8e7b-468">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-468">String</span></span>|  
|<span data-ttu-id="d8e7b-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-470">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d8e7b-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8e7b-471">Procedures</span></span>  
  
|<span data-ttu-id="d8e7b-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-472">ColumnName</span></span>|<span data-ttu-id="d8e7b-473">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-475">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-475">String</span></span>|  
|<span data-ttu-id="d8e7b-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d8e7b-477">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-477">String</span></span>|  
|<span data-ttu-id="d8e7b-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-479">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-479">String</span></span>|  
|<span data-ttu-id="d8e7b-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d8e7b-481">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-481">Int16</span></span>|  
|<span data-ttu-id="d8e7b-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d8e7b-483">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-483">Int16</span></span>|  
|<span data-ttu-id="d8e7b-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d8e7b-485">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-485">Int16</span></span>|  
|<span data-ttu-id="d8e7b-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-486">REMARKS</span></span>|<span data-ttu-id="d8e7b-487">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-487">String</span></span>|  
|<span data-ttu-id="d8e7b-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d8e7b-489">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d8e7b-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8e7b-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d8e7b-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-491">ColumnName</span></span>|<span data-ttu-id="d8e7b-492">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d8e7b-494">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-494">String</span></span>|  
|<span data-ttu-id="d8e7b-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8e7b-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d8e7b-496">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-496">String</span></span>|  
|<span data-ttu-id="d8e7b-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-498">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-498">String</span></span>|  
|<span data-ttu-id="d8e7b-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-499">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-500">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-500">String</span></span>|  
|<span data-ttu-id="d8e7b-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-501">COLUMN_TYPE</span></span>|<span data-ttu-id="d8e7b-502">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-502">Int16</span></span>|  
|<span data-ttu-id="d8e7b-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-503">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-504">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-504">Int16</span></span>|  
|<span data-ttu-id="d8e7b-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-505">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-506">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-506">String</span></span>|  
|<span data-ttu-id="d8e7b-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-507">PRECISION</span></span>|<span data-ttu-id="d8e7b-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-508">Int32</span></span>|  
|<span data-ttu-id="d8e7b-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-509">LENGTH</span></span>|<span data-ttu-id="d8e7b-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-510">Int32</span></span>|  
|<span data-ttu-id="d8e7b-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-511">SCALE</span></span>|<span data-ttu-id="d8e7b-512">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-512">Int16</span></span>|  
|<span data-ttu-id="d8e7b-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-513">RADIX</span></span>|<span data-ttu-id="d8e7b-514">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-514">Int16</span></span>|  
|<span data-ttu-id="d8e7b-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-515">NULLABLE</span></span>|<span data-ttu-id="d8e7b-516">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-516">Int16</span></span>|  
|<span data-ttu-id="d8e7b-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-517">REMARKS</span></span>|<span data-ttu-id="d8e7b-518">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-518">String</span></span>|  
|<span data-ttu-id="d8e7b-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d8e7b-519">OVERLOAD</span></span>|<span data-ttu-id="d8e7b-520">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-520">Int32</span></span>|  
|<span data-ttu-id="d8e7b-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-522">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d8e7b-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8e7b-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d8e7b-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="d8e7b-524">ColumnName</span></span>|<span data-ttu-id="d8e7b-525">DataType</span><span class="sxs-lookup"><span data-stu-id="d8e7b-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8e7b-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d8e7b-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="d8e7b-527">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-527">String</span></span>|  
|<span data-ttu-id="d8e7b-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d8e7b-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d8e7b-529">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-529">String</span></span>|  
|<span data-ttu-id="d8e7b-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8e7b-531">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-531">String</span></span>|  
|<span data-ttu-id="d8e7b-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-532">COLUMN_NAME</span></span>|<span data-ttu-id="d8e7b-533">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-533">String</span></span>|  
|<span data-ttu-id="d8e7b-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-534">COLUMN_TYPE</span></span>|<span data-ttu-id="d8e7b-535">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-535">Int16</span></span>|  
|<span data-ttu-id="d8e7b-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-536">DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-537">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-537">Int16</span></span>|  
|<span data-ttu-id="d8e7b-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8e7b-538">TYPE_NAME</span></span>|<span data-ttu-id="d8e7b-539">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-539">String</span></span>|  
|<span data-ttu-id="d8e7b-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-540">COLUMN_SIZE</span></span>|<span data-ttu-id="d8e7b-541">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-541">Int32</span></span>|  
|<span data-ttu-id="d8e7b-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="d8e7b-543">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-543">Int32</span></span>|  
|<span data-ttu-id="d8e7b-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d8e7b-545">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-545">Int16</span></span>|  
|<span data-ttu-id="d8e7b-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d8e7b-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d8e7b-547">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-547">Int16</span></span>|  
|<span data-ttu-id="d8e7b-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-548">NULLABLE</span></span>|<span data-ttu-id="d8e7b-549">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-549">Int16</span></span>|  
|<span data-ttu-id="d8e7b-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d8e7b-550">REMARKS</span></span>|<span data-ttu-id="d8e7b-551">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-551">String</span></span>|  
|<span data-ttu-id="d8e7b-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d8e7b-552">COLUMN_DEF</span></span>|<span data-ttu-id="d8e7b-553">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-553">String</span></span>|  
|<span data-ttu-id="d8e7b-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d8e7b-555">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-555">Int16</span></span>|  
|<span data-ttu-id="d8e7b-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d8e7b-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d8e7b-557">Int16</span><span class="sxs-lookup"><span data-stu-id="d8e7b-557">Int16</span></span>|  
|<span data-ttu-id="d8e7b-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8e7b-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d8e7b-559">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-559">Int32</span></span>|  
|<span data-ttu-id="d8e7b-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8e7b-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8e7b-561">Int32</span><span class="sxs-lookup"><span data-stu-id="d8e7b-561">Int32</span></span>|  
|<span data-ttu-id="d8e7b-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8e7b-562">IS_NULLABLE</span></span>|<span data-ttu-id="d8e7b-563">String</span><span class="sxs-lookup"><span data-stu-id="d8e7b-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8e7b-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8e7b-564">See Also</span></span>  
 [<span data-ttu-id="d8e7b-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="d8e7b-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
