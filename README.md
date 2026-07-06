## Configuration

Rate Limiter App v1 currently uses the following hardcoded configuration:

| Parameter | Current Value | Description |
|-----------|---------------|-------------|
| `maxAllowedRequests` | `500 requests/minute` | Maximum number of requests allowed globally within the sliding window |
| `maxAllowedRequestsPerUser` | `500 requests/minute` | Maximum number of requests allowed per user within the sliding window |

The current implementation supports:
- Global rate limiting using a fixed limit of 500 requests/minute.
- Per-user rate limiting using a fixed limit of 500 requests/minute.

## Future Enhancements

Potential improvements planned for future versions:

- Replace in-memory timestamp queue storage with a more memory-efficient rate limiting algorithm such as Sliding Window Counter or Token Bucket
- Move rate limit state to a distributed store such as Redis to support horizontal scaling across multiple service instances
- Make `maxAllowedRequests` and `maxAllowedRequestsPerUser` configurable through application properties/environment variables
- Support dynamic rate limit configuration without requiring application redeployment
- Add metrics and monitoring dashboards for rate limit usage and rejected requests
- Implement distributed rate limiting for multi-instance deployments
