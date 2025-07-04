package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/messaging"
)

func main() {
    client := client.New(
        client.WithEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
        client.WithProject("<YOUR_PROJECT_ID>") // Your project ID
        client.WithKey("<YOUR_API_KEY>") // Your secret API key
    )

    service := messaging.New(client)
    response, error := service.CreatePush(
        "<MESSAGE_ID>",
        messaging.WithCreatePushTitle("<TITLE>"),
        messaging.WithCreatePushBody("<BODY>"),
        messaging.WithCreatePushTopics([]interface{}{}),
        messaging.WithCreatePushUsers([]interface{}{}),
        messaging.WithCreatePushTargets([]interface{}{}),
        messaging.WithCreatePushData(map[string]interface{}{}),
        messaging.WithCreatePushAction("<ACTION>"),
        messaging.WithCreatePushImage("[ID1:ID2]"),
        messaging.WithCreatePushIcon("<ICON>"),
        messaging.WithCreatePushSound("<SOUND>"),
        messaging.WithCreatePushColor("<COLOR>"),
        messaging.WithCreatePushTag("<TAG>"),
        messaging.WithCreatePushBadge(0),
        messaging.WithCreatePushDraft(false),
        messaging.WithCreatePushScheduledAt(""),
        messaging.WithCreatePushContentAvailable(false),
        messaging.WithCreatePushCritical(false),
        messaging.WithCreatePushPriority("normal"),
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}
