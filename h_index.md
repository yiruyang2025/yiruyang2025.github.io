#!/usr/bin/env python3
import sys


def h_index(citations):
    citations = sorted(citations, reverse=True)
    h = 0
    for i, c in enumerate(citations, start=1):
        if c >= i:
            h = i
        else:
            break
    return h


def i10_index(citations):
    return sum(1 for c in citations if c >= 10)


def main():
    data = sys.stdin.read().strip()
    if not data:
        print("No input provided.", file=sys.stderr)
        sys.exit(1)

    try:
        citations = list(map(int, data.split()))
    except ValueError:
        print("Input must be integers only.", file=sys.stderr)
        sys.exit(1)

    h = h_index(citations)
    i10 = i10_index(citations)

    print(f"h-index: {h}")
    print(f"i10-index: {i10}")


if __name__ == "__main__":
    main()
