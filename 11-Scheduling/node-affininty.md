# Node Affinty
Used to acheive complex node filteration scenarios

## How to? 
    spec: 
      affinity:
        nodeAffinity: 
          requiredDuringSchedulingIgnoredDuringExecution: 
            nodeSelectorTerms:
            - matchExpressions: 
              - key: "color"
                operator: "In"
                values: 
                  - "blue"