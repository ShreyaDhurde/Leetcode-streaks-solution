class Solution:
    def __init__(self):
        self.effort = [[float('inf')] * 105 for _ in range(105)]
        self.dx = [0, 1, -1, 0]
        self.dy = [1, 0, 0, -1]

    def dijkstra(self, heights) -> int:
        rows = len(heights)
        cols = len(heights[0])

        pq = [(0, 0, 0)]  # Priority queue to store (-effort, x, y)
        self.effort[0][0] = 0  # Initial effort at the starting cell

        while pq:
            cost, x, y = heapq.heappop(pq)

            # Skip if we've already found a better effort for this cell
            if cost > self.effort[x][y]:
                continue

            # Stop if we've reached the bottom-right cell
            if x == rows - 1 and y == cols - 1:
                return cost

            # Explore each direction (up, down, left, right)
            for i in range(4):
                new_x = x + self.dx[i]
                new_y = y + self.dy[i]

                # Check if the new coordinates are within bounds
                if not (0 <= new_x < rows and 0 <= new_y < cols):
                    continue

                # Calculate new effort for the neighboring cell
                new_effort = max(self.effort[x][y], abs(heights[x][y] - heights[new_x][new_y]))

                # Update effort if a lower effort is found for the neighboring cell
                if new_effort < self.effort[new_x][new_y]:
                    self.effort[new_x][new_y] = new_effort
                    heapq.heappush(pq, (new_effort, new_x, new_y))

        return self.effort[rows - 1][cols - 1]  # Minimum effort for the path to the bottom-right cell

    def minimumEffortPath(self, heights) -> int:
        rows = len(heights)
        cols = len(heights[0])

        # Initialize effort for each cell to maximum value
        for i in range(rows):
            for j in range(cols):
                self.effort[i][j] = float('inf')

        return self.dijkstra(heights)  # Find minimum effort using dijkstra
