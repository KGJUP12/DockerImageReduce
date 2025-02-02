###############################
# Stage-1
####################
FROM ubuntu as build

RUN  apt update &&  apt install -y golang-go

ENV GO111MODULE=off

COPY . .

RUN CGO_ENABLED=0 go build -o /app

#######################
#Stage-2
##############################

FROM scratch    

COPY --from=build /app /app

ENTRYPOINT ["/app"]
