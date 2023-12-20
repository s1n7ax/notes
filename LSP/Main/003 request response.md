# Request Response Messages

## Request

- Every processed request must send a response back to the sender

```typescript
/**
 * Abstract message of JSON-RPC
 */
interface Message {
  jsonrpc: string;
}

interface RequestMessage extends Message {
  /**
   * The request id.
   */
  id: integer | string;

  /**
   * The method to be invoked.
   */
  method: string;

  /**
   * The method's params.
   */
  params?: array | object;
}
```

## Response

```typescript
interface ResponseMessage extends Message {
  /**
   * The request id.
   */
  id: integer | string | null;

  /**
   * The result of a request. This member is REQUIRED on success.
   * This member MUST NOT exist if there was an error invoking the method.
   */
  result?: string | number | boolean | array | object | null;

  /**
   * The error object in case a request fails.
   */
  error?: ResponseError;
}

interface ResponseError {
  /**
   * A number indicating the error type that occurred.
   */
  code: integer;

  /**
   * A string providing a short description of the error.
   */
  message: string;

  /**
   * A primitive or structured value that contains additional
   * information about the error. Can be omitted.
   */
  data?: string | number | boolean | array | object | null;
}
```
