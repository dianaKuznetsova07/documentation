asyncapi: 2.6.0
info:
  title: BookstoreOrder
  version: 1.0.0
servers:
  amqp:
    url: amqp://localhost:5672
channels:
  orderStatusUpdates:
    subscribe:
      message:
        $ref: '#/components/messages/OrderStatusUpdate'
components:
  messages:
    OrderStatusUpdate:
      payload:
        $ref: '#/components/schemas/OrderStatus'
  schemas:
    OrderStatus:
      type: object
      properties:
        orderId:
          type: integer
          format: int64
        userId:
          type: integer
          format: int64
        status:
          type: string
          enum: [pending, processing, shipped, delivered]
        timestamp:
          type: string
          format: date-time