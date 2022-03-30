FROM mcr.microsoft.com/dotnet/sdk:5.0-alpine as build
WORKDIR /app

COPY *.sln .
COPY TheatricalPlayersRefactoringKata/*.csproj ./TheatricalPlayersRefactoringKata/
COPY TheatricalPlayersRefactoringKata.Tests/*.csproj ./TheatricalPlayersRefactoringKata.Tests/
RUN dotnet restore

COPY . .
RUN dotnet build

FROM build AS test
RUN dotnet test --logger:console;verbosity=detailed