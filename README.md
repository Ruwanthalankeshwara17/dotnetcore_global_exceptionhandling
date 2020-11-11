# dotnetcore3.1_global_exceptionhandling 

# Used Technologies

1. dotnetcore 3.1

# Quick Started

1. Checkout the code.
2. Open a cmd inside the folder where you cloned the code.
3. Run 'dotnet run --project ./GlobalExceptionHandling.csproj' or 'dotnet run'
4. Open a browser and type 'https://localhost:5000'

# Getting Started

Create a web api project and navigate to the Configure method. There exception handling done only for development enviorenment. Though it is no exception handling middleware,
ASP.NET Core catch the exception from it's infrastructure, log it and return a blank 500 page to client.

Let's customize this further. There are 2 options. 
1. Write custom exception handler.
2. Use Built-in middleware.

Second approach is the safer option since it handles most of the edge cases.

First add GlobalExceptionHandler class.
Then add UseGlobalExceptionHandler function. In WriteResponse method write details flag is set based on the environment.

Finally implement the Write response method. This retrieves exception from ExceptionHandlerMiddleware using IExceptionHandlerFeature and build a ProblemDetails object and write the object to response stream.

Finally add it to the HTTP Request pipeline.
