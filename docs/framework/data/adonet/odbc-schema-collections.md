---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479985"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="9ced8-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="9ced8-102">ODBC Schema Collections</span></span>
<span data-ttu-id="9ced8-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="9ced8-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="9ced8-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ced8-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="9ced8-105">El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="9ced8-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9ced8-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="9ced8-106">Tables</span></span>  
  
-   <span data-ttu-id="9ced8-107">Índices</span><span class="sxs-lookup"><span data-stu-id="9ced8-107">Indexes</span></span>  
  
-   <span data-ttu-id="9ced8-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="9ced8-108">Columns</span></span>  
  
-   <span data-ttu-id="9ced8-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced8-109">Procedures</span></span>  
  
-   <span data-ttu-id="9ced8-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ced8-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9ced8-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ced8-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9ced8-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="9ced8-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="9ced8-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="9ced8-113">Tables and Views</span></span>  
  
|<span data-ttu-id="9ced8-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-114">ColumnName</span></span>|<span data-ttu-id="9ced8-115">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9ced8-116">TABLE_CAT</span></span>|<span data-ttu-id="9ced8-117">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-117">String</span></span>|  
|<span data-ttu-id="9ced8-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9ced8-118">TABLE_SCHEM</span></span>|<span data-ttu-id="9ced8-119">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-119">String</span></span>|  
|<span data-ttu-id="9ced8-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-120">TABLE_NAME</span></span>|<span data-ttu-id="9ced8-121">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-121">String</span></span>|  
|<span data-ttu-id="9ced8-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-122">TABLE_TYPE</span></span>|<span data-ttu-id="9ced8-123">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-123">String</span></span>|  
|<span data-ttu-id="9ced8-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-124">REMARKS</span></span>|<span data-ttu-id="9ced8-125">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9ced8-126">Índices</span><span class="sxs-lookup"><span data-stu-id="9ced8-126">Indexes</span></span>  
  
|<span data-ttu-id="9ced8-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-127">ColumnName</span></span>|<span data-ttu-id="9ced8-128">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9ced8-129">TABLE_CAT</span></span>|<span data-ttu-id="9ced8-130">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-130">String</span></span>|  
|<span data-ttu-id="9ced8-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9ced8-131">TABLE_SCHEM</span></span>|<span data-ttu-id="9ced8-132">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-132">String</span></span>|  
|<span data-ttu-id="9ced8-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-133">TABLE_NAME</span></span>|<span data-ttu-id="9ced8-134">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-134">String</span></span>|  
|<span data-ttu-id="9ced8-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9ced8-135">NON_UNIQUE</span></span>|<span data-ttu-id="9ced8-136">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-136">Int16</span></span>|  
|<span data-ttu-id="9ced8-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="9ced8-138">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-138">String</span></span>|  
|<span data-ttu-id="9ced8-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-139">INDEX_NAME</span></span>|<span data-ttu-id="9ced8-140">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-140">String</span></span>|  
|<span data-ttu-id="9ced8-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-141">TYPE</span></span>|<span data-ttu-id="9ced8-142">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-142">Int16</span></span>|  
|<span data-ttu-id="9ced8-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-144">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-144">Int16</span></span>|  
|<span data-ttu-id="9ced8-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-145">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-146">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-146">String</span></span>|  
|<span data-ttu-id="9ced8-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="9ced8-147">ASC_OR_DESC</span></span>|<span data-ttu-id="9ced8-148">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-148">String</span></span>|  
|<span data-ttu-id="9ced8-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="9ced8-149">CARDINATLITY</span></span>|<span data-ttu-id="9ced8-150">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-150">Int32</span></span>|  
|<span data-ttu-id="9ced8-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="9ced8-151">PAGES</span></span>|<span data-ttu-id="9ced8-152">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-152">Int32</span></span>|  
|<span data-ttu-id="9ced8-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-153">FILTER_CONDITION</span></span>|<span data-ttu-id="9ced8-154">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-154">String</span></span>|  
|<span data-ttu-id="9ced8-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ced8-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9ced8-156">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-156">String</span></span>|  
|<span data-ttu-id="9ced8-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-158">Byte</span><span class="sxs-lookup"><span data-stu-id="9ced8-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9ced8-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="9ced8-159">Columns</span></span>  
  
|<span data-ttu-id="9ced8-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-160">ColumnName</span></span>|<span data-ttu-id="9ced8-161">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9ced8-162">TABLE_CAT</span></span>|<span data-ttu-id="9ced8-163">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-163">String</span></span>|  
|<span data-ttu-id="9ced8-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9ced8-164">TABLE_SCHEM</span></span>|<span data-ttu-id="9ced8-165">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-165">String</span></span>|  
|<span data-ttu-id="9ced8-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-166">TABLE_NAME</span></span>|<span data-ttu-id="9ced8-167">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-167">String</span></span>|  
|<span data-ttu-id="9ced8-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-168">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-169">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-169">String</span></span>|  
|<span data-ttu-id="9ced8-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-170">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-171">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-171">Int16</span></span>|  
|<span data-ttu-id="9ced8-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-172">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-173">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-173">String</span></span>|  
|<span data-ttu-id="9ced8-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9ced8-174">COLUMN_SIZE</span></span>|<span data-ttu-id="9ced8-175">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-175">Int32</span></span>|  
|<span data-ttu-id="9ced8-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="9ced8-177">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-177">Int32</span></span>|  
|<span data-ttu-id="9ced8-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9ced8-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9ced8-179">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-179">Int16</span></span>|  
|<span data-ttu-id="9ced8-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9ced8-181">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-181">Int16</span></span>|  
|<span data-ttu-id="9ced8-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-182">NULLABLE</span></span>|<span data-ttu-id="9ced8-183">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-183">Int16</span></span>|  
|<span data-ttu-id="9ced8-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-184">REMARKS</span></span>|<span data-ttu-id="9ced8-185">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-185">String</span></span>|  
|<span data-ttu-id="9ced8-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9ced8-186">COLUMN_DEF</span></span>|<span data-ttu-id="9ced8-187">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-187">String</span></span>|  
|<span data-ttu-id="9ced8-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-189">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-189">Int16</span></span>|  
|<span data-ttu-id="9ced8-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9ced8-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9ced8-191">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-191">Int16</span></span>|  
|<span data-ttu-id="9ced8-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9ced8-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-193">Int32</span></span>|  
|<span data-ttu-id="9ced8-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-195">Int32</span></span>|  
|<span data-ttu-id="9ced8-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-196">IS_NULLABLE</span></span>|<span data-ttu-id="9ced8-197">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-197">String</span></span>|  
|<span data-ttu-id="9ced8-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ced8-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9ced8-199">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-199">String</span></span>|  
|<span data-ttu-id="9ced8-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ced8-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9ced8-201">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-201">String</span></span>|  
|<span data-ttu-id="9ced8-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-203">Byte</span><span class="sxs-lookup"><span data-stu-id="9ced8-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9ced8-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced8-204">Procedures</span></span>  
  
|<span data-ttu-id="9ced8-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-205">ColumnName</span></span>|<span data-ttu-id="9ced8-206">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9ced8-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="9ced8-208">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-208">String</span></span>|  
|<span data-ttu-id="9ced8-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9ced8-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9ced8-210">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-210">String</span></span>|  
|<span data-ttu-id="9ced8-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-212">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-212">String</span></span>|  
|<span data-ttu-id="9ced8-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9ced8-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9ced8-214">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-214">Int32</span></span>|  
|<span data-ttu-id="9ced8-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9ced8-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9ced8-216">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-216">Int32</span></span>|  
|<span data-ttu-id="9ced8-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9ced8-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9ced8-218">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-218">Int32</span></span>|  
|<span data-ttu-id="9ced8-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-219">REMARKS</span></span>|<span data-ttu-id="9ced8-220">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-220">String</span></span>|  
|<span data-ttu-id="9ced8-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9ced8-222">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9ced8-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ced8-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9ced8-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-224">ColumnName</span></span>|<span data-ttu-id="9ced8-225">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9ced8-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="9ced8-227">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-227">String</span></span>|  
|<span data-ttu-id="9ced8-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9ced8-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9ced8-229">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-229">String</span></span>|  
|<span data-ttu-id="9ced8-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-231">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-231">String</span></span>|  
|<span data-ttu-id="9ced8-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-232">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-233">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-233">String</span></span>|  
|<span data-ttu-id="9ced8-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-234">COLUMN_TYPE</span></span>|<span data-ttu-id="9ced8-235">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-235">Int16</span></span>|  
|<span data-ttu-id="9ced8-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-236">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-237">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-237">Int16</span></span>|  
|<span data-ttu-id="9ced8-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-238">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-239">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-239">String</span></span>|  
|<span data-ttu-id="9ced8-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9ced8-240">COLUMN_SIZE</span></span>|<span data-ttu-id="9ced8-241">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-241">Int32</span></span>|  
|<span data-ttu-id="9ced8-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="9ced8-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-243">Int32</span></span>|  
|<span data-ttu-id="9ced8-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9ced8-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9ced8-245">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-245">Int16</span></span>|  
|<span data-ttu-id="9ced8-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9ced8-247">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-247">Int16</span></span>|  
|<span data-ttu-id="9ced8-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-248">NULLABLE</span></span>|<span data-ttu-id="9ced8-249">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-249">Int16</span></span>|  
|<span data-ttu-id="9ced8-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-250">REMARKS</span></span>|<span data-ttu-id="9ced8-251">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-251">String</span></span>|  
|<span data-ttu-id="9ced8-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9ced8-252">COLUMN_DEF</span></span>|<span data-ttu-id="9ced8-253">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-253">String</span></span>|  
|<span data-ttu-id="9ced8-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-255">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-255">Int16</span></span>|  
|<span data-ttu-id="9ced8-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9ced8-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9ced8-257">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-257">Int16</span></span>|  
|<span data-ttu-id="9ced8-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9ced8-259">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-259">Int32</span></span>|  
|<span data-ttu-id="9ced8-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-261">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-261">Int32</span></span>|  
|<span data-ttu-id="9ced8-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-262">IS_NULLABLE</span></span>|<span data-ttu-id="9ced8-263">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-263">String</span></span>|  
|<span data-ttu-id="9ced8-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ced8-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9ced8-265">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-265">String</span></span>|  
|<span data-ttu-id="9ced8-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ced8-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9ced8-267">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-267">String</span></span>|  
|<span data-ttu-id="9ced8-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-269">Byte</span><span class="sxs-lookup"><span data-stu-id="9ced8-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9ced8-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ced8-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9ced8-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-271">ColumnName</span></span>|<span data-ttu-id="9ced8-272">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9ced8-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="9ced8-274">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-274">String</span></span>|  
|<span data-ttu-id="9ced8-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9ced8-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9ced8-276">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-276">String</span></span>|  
|<span data-ttu-id="9ced8-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-278">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-278">String</span></span>|  
|<span data-ttu-id="9ced8-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-279">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-280">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-280">String</span></span>|  
|<span data-ttu-id="9ced8-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-281">COLUMN_TYPE</span></span>|<span data-ttu-id="9ced8-282">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-282">Int16</span></span>|  
|<span data-ttu-id="9ced8-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-283">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-284">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-284">Int16</span></span>|  
|<span data-ttu-id="9ced8-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-285">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-286">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-286">String</span></span>|  
|<span data-ttu-id="9ced8-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9ced8-287">COLUMN_SIZE</span></span>|<span data-ttu-id="9ced8-288">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-288">Int32</span></span>|  
|<span data-ttu-id="9ced8-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="9ced8-290">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-290">Int32</span></span>|  
|<span data-ttu-id="9ced8-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9ced8-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9ced8-292">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-292">Int16</span></span>|  
|<span data-ttu-id="9ced8-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9ced8-294">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-294">Int16</span></span>|  
|<span data-ttu-id="9ced8-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-295">NULLABLE</span></span>|<span data-ttu-id="9ced8-296">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-296">Int16</span></span>|  
|<span data-ttu-id="9ced8-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-297">REMARKS</span></span>|<span data-ttu-id="9ced8-298">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-298">String</span></span>|  
|<span data-ttu-id="9ced8-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9ced8-299">COLUMN_DEF</span></span>|<span data-ttu-id="9ced8-300">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-300">String</span></span>|  
|<span data-ttu-id="9ced8-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-302">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-302">Int16</span></span>|  
|<span data-ttu-id="9ced8-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9ced8-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9ced8-304">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-304">Int16</span></span>|  
|<span data-ttu-id="9ced8-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9ced8-306">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-306">Int32</span></span>|  
|<span data-ttu-id="9ced8-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-308">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-308">Int32</span></span>|  
|<span data-ttu-id="9ced8-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-309">IS_NULLABLE</span></span>|<span data-ttu-id="9ced8-310">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-310">String</span></span>|  
|<span data-ttu-id="9ced8-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ced8-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9ced8-312">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-312">String</span></span>|  
|<span data-ttu-id="9ced8-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9ced8-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9ced8-314">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-314">String</span></span>|  
|<span data-ttu-id="9ced8-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-316">Byte</span><span class="sxs-lookup"><span data-stu-id="9ced8-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="9ced8-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ced8-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="9ced8-318">El controlador ODBC de Oracle de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="9ced8-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9ced8-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="9ced8-319">Tables</span></span>  
  
-   <span data-ttu-id="9ced8-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="9ced8-320">Columns</span></span>  
  
-   <span data-ttu-id="9ced8-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced8-321">Procedures</span></span>  
  
-   <span data-ttu-id="9ced8-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ced8-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9ced8-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ced8-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9ced8-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="9ced8-324">Views</span></span>  
  
-   <span data-ttu-id="9ced8-325">Índices</span><span class="sxs-lookup"><span data-stu-id="9ced8-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="9ced8-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="9ced8-326">Tables and Views</span></span>  
  
|<span data-ttu-id="9ced8-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-327">ColumnName</span></span>|<span data-ttu-id="9ced8-328">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-330">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-330">String</span></span>|  
|<span data-ttu-id="9ced8-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-331">TABLE_OWNER</span></span>|<span data-ttu-id="9ced8-332">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-332">String</span></span>|  
|<span data-ttu-id="9ced8-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-333">TABLE_NAME</span></span>|<span data-ttu-id="9ced8-334">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-334">String</span></span>|  
|<span data-ttu-id="9ced8-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-335">TABLE_TYPE</span></span>|<span data-ttu-id="9ced8-336">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-336">String</span></span>|  
|<span data-ttu-id="9ced8-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-337">REMARKS</span></span>|<span data-ttu-id="9ced8-338">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9ced8-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="9ced8-339">Columns</span></span>  
  
|<span data-ttu-id="9ced8-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-340">ColumnName</span></span>|<span data-ttu-id="9ced8-341">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-343">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-343">String</span></span>|  
|<span data-ttu-id="9ced8-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-344">TABLE_OWNER</span></span>|<span data-ttu-id="9ced8-345">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-345">String</span></span>|  
|<span data-ttu-id="9ced8-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-346">TABLE_NAME</span></span>|<span data-ttu-id="9ced8-347">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-347">String</span></span>|  
|<span data-ttu-id="9ced8-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-348">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-349">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-349">String</span></span>|  
|<span data-ttu-id="9ced8-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-350">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-351">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-351">Int16</span></span>|  
|<span data-ttu-id="9ced8-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-352">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-353">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-353">String</span></span>|  
|<span data-ttu-id="9ced8-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ced8-354">PRECISION</span></span>|<span data-ttu-id="9ced8-355">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-355">Int32</span></span>|  
|<span data-ttu-id="9ced8-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-356">LENGTH</span></span>|<span data-ttu-id="9ced8-357">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-357">Int32</span></span>|  
|<span data-ttu-id="9ced8-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="9ced8-358">SCALE</span></span>|<span data-ttu-id="9ced8-359">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-359">Int16</span></span>|  
|<span data-ttu-id="9ced8-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-360">RADIX</span></span>|<span data-ttu-id="9ced8-361">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-361">Int16</span></span>|  
|<span data-ttu-id="9ced8-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-362">NULLABLE</span></span>|<span data-ttu-id="9ced8-363">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-363">Int16</span></span>|  
|<span data-ttu-id="9ced8-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-364">REMARKS</span></span>|<span data-ttu-id="9ced8-365">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-365">String</span></span>|  
|<span data-ttu-id="9ced8-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-367">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9ced8-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced8-368">Procedures</span></span>  
  
|<span data-ttu-id="9ced8-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-369">ColumnName</span></span>|<span data-ttu-id="9ced8-370">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-372">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-372">String</span></span>|  
|<span data-ttu-id="9ced8-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9ced8-374">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-374">String</span></span>|  
|<span data-ttu-id="9ced8-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-376">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-376">String</span></span>|  
|<span data-ttu-id="9ced8-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9ced8-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9ced8-378">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-378">Int16</span></span>|  
|<span data-ttu-id="9ced8-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9ced8-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9ced8-380">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-380">Int16</span></span>|  
|<span data-ttu-id="9ced8-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9ced8-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9ced8-382">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-382">Int16</span></span>|  
|<span data-ttu-id="9ced8-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-383">REMARKS</span></span>|<span data-ttu-id="9ced8-384">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-384">String</span></span>|  
|<span data-ttu-id="9ced8-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9ced8-386">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9ced8-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ced8-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9ced8-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-388">ColumnName</span></span>|<span data-ttu-id="9ced8-389">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-391">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-391">String</span></span>|  
|<span data-ttu-id="9ced8-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9ced8-393">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-393">String</span></span>|  
|<span data-ttu-id="9ced8-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-395">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-395">String</span></span>|  
|<span data-ttu-id="9ced8-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-396">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-397">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-397">String</span></span>|  
|<span data-ttu-id="9ced8-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-398">COLUMN_TYPE</span></span>|<span data-ttu-id="9ced8-399">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-399">Int16</span></span>|  
|<span data-ttu-id="9ced8-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-400">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-401">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-401">Int16</span></span>|  
|<span data-ttu-id="9ced8-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-402">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-403">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-403">String</span></span>|  
|<span data-ttu-id="9ced8-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ced8-404">PRECISION</span></span>|<span data-ttu-id="9ced8-405">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-405">Int32</span></span>|  
|<span data-ttu-id="9ced8-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-406">LENGTH</span></span>|<span data-ttu-id="9ced8-407">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-407">Int32</span></span>|  
|<span data-ttu-id="9ced8-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="9ced8-408">SCALE</span></span>|<span data-ttu-id="9ced8-409">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-409">Int16</span></span>|  
|<span data-ttu-id="9ced8-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-410">RADIX</span></span>|<span data-ttu-id="9ced8-411">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-411">Int16</span></span>|  
|<span data-ttu-id="9ced8-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-412">NULLABLE</span></span>|<span data-ttu-id="9ced8-413">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-413">Int16</span></span>|  
|<span data-ttu-id="9ced8-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-414">REMARKS</span></span>|<span data-ttu-id="9ced8-415">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-415">String</span></span>|  
|<span data-ttu-id="9ced8-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9ced8-416">OVERLOAD</span></span>|<span data-ttu-id="9ced8-417">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-417">Int32</span></span>|  
|<span data-ttu-id="9ced8-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-419">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="9ced8-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="9ced8-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="9ced8-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="9ced8-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9ced8-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="9ced8-422">Tables</span></span>  
  
-   <span data-ttu-id="9ced8-423">Índices</span><span class="sxs-lookup"><span data-stu-id="9ced8-423">Indexes</span></span>  
  
-   <span data-ttu-id="9ced8-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="9ced8-424">Columns</span></span>  
  
-   <span data-ttu-id="9ced8-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced8-425">Procedures</span></span>  
  
-   <span data-ttu-id="9ced8-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ced8-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9ced8-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ced8-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9ced8-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="9ced8-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="9ced8-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="9ced8-429">Tables and Views</span></span>  
  
|<span data-ttu-id="9ced8-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-430">ColumnName</span></span>|<span data-ttu-id="9ced8-431">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-433">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-433">String</span></span>|  
|<span data-ttu-id="9ced8-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-434">TABLE_OWNER</span></span>|<span data-ttu-id="9ced8-435">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-435">String</span></span>|  
|<span data-ttu-id="9ced8-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-436">TABLE_NAME</span></span>|<span data-ttu-id="9ced8-437">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-437">String</span></span>|  
|<span data-ttu-id="9ced8-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-438">TABLE_TYPE</span></span>|<span data-ttu-id="9ced8-439">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-439">String</span></span>|  
|<span data-ttu-id="9ced8-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-440">REMARKS</span></span>|<span data-ttu-id="9ced8-441">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9ced8-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="9ced8-442">Columns</span></span>  
  
|<span data-ttu-id="9ced8-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-443">ColumnName</span></span>|<span data-ttu-id="9ced8-444">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-446">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-446">String</span></span>|  
|<span data-ttu-id="9ced8-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-447">TABLE_OWNER</span></span>|<span data-ttu-id="9ced8-448">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-448">String</span></span>|  
|<span data-ttu-id="9ced8-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-449">TABLE_NAME</span></span>|<span data-ttu-id="9ced8-450">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-450">String</span></span>|  
|<span data-ttu-id="9ced8-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-451">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-452">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-452">String</span></span>|  
|<span data-ttu-id="9ced8-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-453">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-454">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-454">Int16</span></span>|  
|<span data-ttu-id="9ced8-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-455">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-456">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-456">String</span></span>|  
|<span data-ttu-id="9ced8-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ced8-457">PRECISION</span></span>|<span data-ttu-id="9ced8-458">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-458">Int32</span></span>|  
|<span data-ttu-id="9ced8-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-459">LENGTH</span></span>|<span data-ttu-id="9ced8-460">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-460">Int32</span></span>|  
|<span data-ttu-id="9ced8-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="9ced8-461">SCALE</span></span>|<span data-ttu-id="9ced8-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-462">Int16</span></span>|  
|<span data-ttu-id="9ced8-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-463">RADIX</span></span>|<span data-ttu-id="9ced8-464">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-464">Int16</span></span>|  
|<span data-ttu-id="9ced8-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-465">NULLABLE</span></span>|<span data-ttu-id="9ced8-466">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-466">Int16</span></span>|  
|<span data-ttu-id="9ced8-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-467">REMARKS</span></span>|<span data-ttu-id="9ced8-468">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-468">String</span></span>|  
|<span data-ttu-id="9ced8-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-470">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9ced8-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced8-471">Procedures</span></span>  
  
|<span data-ttu-id="9ced8-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-472">ColumnName</span></span>|<span data-ttu-id="9ced8-473">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-475">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-475">String</span></span>|  
|<span data-ttu-id="9ced8-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9ced8-477">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-477">String</span></span>|  
|<span data-ttu-id="9ced8-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-479">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-479">String</span></span>|  
|<span data-ttu-id="9ced8-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9ced8-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9ced8-481">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-481">Int16</span></span>|  
|<span data-ttu-id="9ced8-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9ced8-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9ced8-483">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-483">Int16</span></span>|  
|<span data-ttu-id="9ced8-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9ced8-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9ced8-485">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-485">Int16</span></span>|  
|<span data-ttu-id="9ced8-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-486">REMARKS</span></span>|<span data-ttu-id="9ced8-487">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-487">String</span></span>|  
|<span data-ttu-id="9ced8-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9ced8-489">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9ced8-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9ced8-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9ced8-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-491">ColumnName</span></span>|<span data-ttu-id="9ced8-492">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9ced8-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9ced8-494">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-494">String</span></span>|  
|<span data-ttu-id="9ced8-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ced8-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9ced8-496">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-496">String</span></span>|  
|<span data-ttu-id="9ced8-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-498">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-498">String</span></span>|  
|<span data-ttu-id="9ced8-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-499">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-500">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-500">String</span></span>|  
|<span data-ttu-id="9ced8-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-501">COLUMN_TYPE</span></span>|<span data-ttu-id="9ced8-502">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-502">Int16</span></span>|  
|<span data-ttu-id="9ced8-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-503">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-504">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-504">Int16</span></span>|  
|<span data-ttu-id="9ced8-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-505">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-506">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-506">String</span></span>|  
|<span data-ttu-id="9ced8-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9ced8-507">PRECISION</span></span>|<span data-ttu-id="9ced8-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-508">Int32</span></span>|  
|<span data-ttu-id="9ced8-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-509">LENGTH</span></span>|<span data-ttu-id="9ced8-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-510">Int32</span></span>|  
|<span data-ttu-id="9ced8-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="9ced8-511">SCALE</span></span>|<span data-ttu-id="9ced8-512">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-512">Int16</span></span>|  
|<span data-ttu-id="9ced8-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-513">RADIX</span></span>|<span data-ttu-id="9ced8-514">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-514">Int16</span></span>|  
|<span data-ttu-id="9ced8-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-515">NULLABLE</span></span>|<span data-ttu-id="9ced8-516">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-516">Int16</span></span>|  
|<span data-ttu-id="9ced8-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-517">REMARKS</span></span>|<span data-ttu-id="9ced8-518">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-518">String</span></span>|  
|<span data-ttu-id="9ced8-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9ced8-519">OVERLOAD</span></span>|<span data-ttu-id="9ced8-520">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-520">Int32</span></span>|  
|<span data-ttu-id="9ced8-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-522">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9ced8-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9ced8-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9ced8-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="9ced8-524">ColumnName</span></span>|<span data-ttu-id="9ced8-525">DataType</span><span class="sxs-lookup"><span data-stu-id="9ced8-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9ced8-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9ced8-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="9ced8-527">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-527">String</span></span>|  
|<span data-ttu-id="9ced8-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9ced8-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9ced8-529">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-529">String</span></span>|  
|<span data-ttu-id="9ced8-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="9ced8-531">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-531">String</span></span>|  
|<span data-ttu-id="9ced8-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-532">COLUMN_NAME</span></span>|<span data-ttu-id="9ced8-533">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-533">String</span></span>|  
|<span data-ttu-id="9ced8-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-534">COLUMN_TYPE</span></span>|<span data-ttu-id="9ced8-535">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-535">Int16</span></span>|  
|<span data-ttu-id="9ced8-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-536">DATA_TYPE</span></span>|<span data-ttu-id="9ced8-537">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-537">Int16</span></span>|  
|<span data-ttu-id="9ced8-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9ced8-538">TYPE_NAME</span></span>|<span data-ttu-id="9ced8-539">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-539">String</span></span>|  
|<span data-ttu-id="9ced8-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9ced8-540">COLUMN_SIZE</span></span>|<span data-ttu-id="9ced8-541">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-541">Int32</span></span>|  
|<span data-ttu-id="9ced8-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="9ced8-543">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-543">Int32</span></span>|  
|<span data-ttu-id="9ced8-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9ced8-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9ced8-545">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-545">Int16</span></span>|  
|<span data-ttu-id="9ced8-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9ced8-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9ced8-547">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-547">Int16</span></span>|  
|<span data-ttu-id="9ced8-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-548">NULLABLE</span></span>|<span data-ttu-id="9ced8-549">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-549">Int16</span></span>|  
|<span data-ttu-id="9ced8-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9ced8-550">REMARKS</span></span>|<span data-ttu-id="9ced8-551">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-551">String</span></span>|  
|<span data-ttu-id="9ced8-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9ced8-552">COLUMN_DEF</span></span>|<span data-ttu-id="9ced8-553">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-553">String</span></span>|  
|<span data-ttu-id="9ced8-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9ced8-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9ced8-555">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-555">Int16</span></span>|  
|<span data-ttu-id="9ced8-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9ced8-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9ced8-557">Int16</span><span class="sxs-lookup"><span data-stu-id="9ced8-557">Int16</span></span>|  
|<span data-ttu-id="9ced8-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9ced8-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9ced8-559">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-559">Int32</span></span>|  
|<span data-ttu-id="9ced8-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9ced8-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="9ced8-561">Int32</span><span class="sxs-lookup"><span data-stu-id="9ced8-561">Int32</span></span>|  
|<span data-ttu-id="9ced8-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9ced8-562">IS_NULLABLE</span></span>|<span data-ttu-id="9ced8-563">String</span><span class="sxs-lookup"><span data-stu-id="9ced8-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ced8-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ced8-564">See Also</span></span>  
 [<span data-ttu-id="9ced8-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="9ced8-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
