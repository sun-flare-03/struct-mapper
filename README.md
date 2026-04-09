# struct-mapper

[![Build Status](https://img.shields.io/github/actions/workflow/status/user/struct-mapper/ci.yml?branch=main)]()
[![Go Version](https://img.shields.io/badge/go-1.22+-blue.svg)]()
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> Struct-to-struct mapper with automatic field matching and custom transforms

A Go project focused on solving real-world engineering problems.

## Features

- Context Support: Full context.Context propagation for cancellation and deadlines
- High Performance: Optimized for low-latency, high-throughput workloads
- Graceful Shutdown: Clean shutdown handling with configurable drain timeout

## Getting Started

### Installation

```bash
go get github.com/user/struct-mapper@latest
```

## Usage

```go
package main

import (
	"fmt"
	"github.com/user/struct-mapper"
)

func main() {
	client := structmapper.New(
		structmapper.WithTimeout(30 * time.Second),
	)

	result, err := client.Run(context.Background())
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(result)
}
```

## Configuration

Configuration can be provided via environment variables, a config file, or programmatically.

| Variable | Description | Default |
|----------|-------------|--------|
| `STRUCT_MAPPER_TIMEOUT` | Request timeout in seconds | `30` |
| `STRUCT_MAPPER_RETRIES` | Number of retry attempts | `3` |
| `STRUCT_MAPPER_LOG_LEVEL` | Log verbosity (debug, info, warn, error) | `info` |

## Contributing

Contributions are welcome! Please read the [contributing guidelines](CONTRIBUTING.md) before submitting a pull request.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
