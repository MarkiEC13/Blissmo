#Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
#For more information, please see https://aka.ms/containercompat

#FROM microsoft/dotnet:2.1-aspnetcore-runtime-nanoserver-1803 AS base
#WORKDIR /app
#EXPOSE 80
#EXPOSE 443
#
#FROM microsoft/dotnet:2.1-sdk-nanoserver-1803 AS build
#WORKDIR /src
#COPY ["Blissmo.Sales.Api/Blissmo.Sales.Api.csproj", "Blissmo.Sales.Api/"]
#RUN dotnet restore "Blissmo.Sales.Api/Blissmo.Sales.Api.csproj"
#COPY . .
#WORKDIR "/src/Blissmo.Sales.Api"
#RUN dotnet build "Blissmo.Sales.Api.csproj" -c Release -o /app
#
#FROM build AS publish
#RUN dotnet publish "Blissmo.Sales.Api.csproj" -c Release -o /app
#
#FROM base AS final
#WORKDIR /app
#COPY --from=publish /app .
#ENTRYPOINT ["dotnet", "Blissmo.Sales.Api.dll"]

FROM microsoft/dotnet:2.0-sdk
COPY pub/ /root/
WORKDIR /root/
ENV ASPNETCORE_URLS="http://*:80"
EXPOSE 80/tcp
ENTRYPOINT ["dotnet", "Blissmo.Sales.Api.dll"]


#dotnet publish --configuration=Release -o pub
#docker build . -t blissmo-sales
#docker run -e Version=1.1 -p 9000:80 blissmo-sales
#dotnet --fx-version 2.1.6 pub/Blissmo.Sales.Api.dll

#docker container ls -a
#docker container stop
#docker container rm cc3f2ff51cab cd20b396a061
#docker image ls
#docker image rm 75835a67d134 2a4cca5ac898

#push to docker hub
#docker tag blissmo-sales markie13/blissmo-sales
#docker push markie13/blissmo-sales